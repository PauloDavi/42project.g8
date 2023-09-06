vpath %.c src/mandatory
$if(has_bonus.truthy)$
vpath %.c src/bonus
$endif$

NAME := $name_project;format="snake"$
CFLAGS := -Wextra -Wall -Werror
CFLAGS += -O3 -g3

CC := cc
RM := rm -rf

LIBTF_DIR := ./lib/libft
LIBS := -L\$(LIBTF_DIR) -lft

OBJ_DIR := build
INCLUDE_DIR := include
INCLUDES := -I\$(INCLUDE_DIR) -I\$(LIBTF_DIR)

SRCS := $name_project;format="snake"$.c
OBJS := \$(addprefix \$(OBJ_DIR)/, \$(SRCS:.c=.o))

$if(has_bonus.truthy)$
SRCS_BONUS := $name_project;format="snake"$_bonus.c
OBJS_BONUS := \$(addprefix \$(OBJ_DIR)/, \$(SRCS_BONUS:.c=.o))
$endif$

all: libft \$(NAME)

init_modules: \$(LIBTF_DIR)
	git submodule update --init

update_modules: init_modules
	git submodule foreach git pull origin master --rebase

libft: update_modules
	@\$(MAKE) -C \$(LIBTF_DIR)

\$(OBJ_DIR)/%.o: %.c | \$(OBJ_DIR)
	\$(CC) \$(CFLAGS) \$(INCLUDES) -c \$< -o \$@

\$(OBJ_DIR):
	mkdir -p \$(OBJ_DIR)

\$(LIBTF_DIR):
	mkdir -p \$(LIBTF_DIR)

\$(NAME): \$(OBJS)
	@\$(CC) \$(OBJS) \$(LIBS) \$(INCLUDES) \$(CFLAGS) -o \$(NAME)

$if(has_bonus.truthy)$
bonus: libft \$(OBJS_BONUS)
	@\$(CC) \$(OBJS_BONUS) \$(LIBS) \$(INCLUDES) \$(CFLAGS) -o \$(NAME)
$endif$

clean: 
	@\$(MAKE) -C \$(LIBTF_DIR) clean
	@\$(RM) \$(OBJS)$if(has_bonus.truthy)$ \$(OBJS_BONUS)$endif$

fclean: clean
	@\$(MAKE) -C \$(LIBTF_DIR) fclean
	@\$(RM) \$(NAME)

re: fclean all

$if(has_bonus.truthy)$
rebonus: fclean bonus
$endif$

$if(has_bonus.truthy)$
.PHONY: all clean fclean re bonus rebonus libft update_modules init_modules
$else$
.PHONY: all clean fclean re libft update_modules init_modules
$endif$