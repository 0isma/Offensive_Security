# METASPLOIT FRAMEWORK

Lo que comenzó como un juego, acabo siendo una herramienta de Red Teaming vital. Consolida el trabajo de explotación, ayudando a facilitar tareas como movientos laterales, etc.

Es de tipo open-source, al alcance de cualquiera.

Para cada uno de los exploits, existen varios payloads  (añandiendo variedad).

<br>

## 1. Arranque y comandos básicos

## 1.1 Intro
- Necesario Postgres
- Requerimos actualizarlo a menudo, puesto a que está en continuo desarollo.

- Se arranca con msf console.
    - use
    - back
    - previous
    - show options: estas  opciones se pueden configurar con set.

### 1.2 Base de Datos
Todo aquello que realizamos queda guardado dentro de una base de datos gracias a postgres. Después de haber realizado un scaner, podemos desplegar el comando **service**, mediante el cual podemos ver la información de los resultados.

- services -h
- db_map: funciona igual que nmap
- hosts: info sobre los hosts regiatrados
- workspace: como las ramas de git

### 1.3 El módulo Auxiliar
Para mostrarlos todos

        show auxiliary 
Para buscar menos, usamos la palabra search

        search -h               nos dice los typos de filtrado posibles
        seach type:auxiliary    buscará los módulos auxiliares

Para correr un módulo auxiliar, hay que usar **run** NO exploit

        run aux module

To set a global parameter, we use **setg**

        setg RHOSTS