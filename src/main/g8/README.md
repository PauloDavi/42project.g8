<h1 align="center">
	$name_project;format="capitalize"$
</h1>

<p align="center">
  <img src="https://i.imgur.com/U7aswVo.png" width="140" alt="grade" />
  <img src="https://game.42sp.org.br/static/assets/achievements/$name_project;format="snake"$$if(has_bonus.truthy)$m$else$e$endif$.png" width="120" alt="m" />
</p>

---

<p align="center">
	<b><i>Your Best Project</i></b><br>
</p>

<p align="center">
	<img alt="GitHub code size in bytes" src="https://img.shields.io/github/languages/code-size/$github_user$/$name$?color=lightblue" />
	<img alt="Code language count" src="https://img.shields.io/github/languages/count/$github_user$/$name$?color=yellow" />
	<img alt="GitHub top language" src="https://img.shields.io/github/languages/top/$github_user$/$name$?color=blue" />
	<img alt="GitHub last commit" src="https://img.shields.io/github/last-commit/$github_user$/$name$?color=green" />
</p>

<h3 align="center">
	<a href="#-about-the-project">About</a>
	<span> • </span>
	<a href="#%EF%B8%8F-compile">Compile</a>
	<span> • </span>
	<a href="#-usage">Usage</a>
</h3>

---

## 💡 About the project


## 🛠️ Compile

> The function is written in C language and thus needs the **`gcc` compiler** and some standard **C libraries** to run.

**Using it in your code**

You just need compile code with make:

```shell
make$if(has_bonus.truthy)$ bonus$endif$
```

## 📋 Usage

The basic usability is like:

```bash
./$name_project;format="snake"$
```
