---
title: "{{ replace .Name "-" " " | title }}"
date: {{ .Date }}
draft: true
tags: ["Linux", "Easy", "SQLi"]
categories: ["HackTheBox"]
author: "st0rmESP"
showToc: true
---

## 🛡️ Enumeración
### Nmap
\```bash
nmap -sCV -p- --min-rate 5000 10.10.10.X
\```

## 👣 Explotación
### Punto de entrada
Explicación de la vulnerabilidad...

## 🔑 Post-Explotación
### Escalada de Privilegios
Pasos para llegar a root...

> **Flag:** `HTB{pwned_by_st0rmESP}`
