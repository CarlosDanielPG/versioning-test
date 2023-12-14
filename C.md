# Reglas

- Todas las versiones que tienen x.x.x-<variante>.<incremento> deben publicarse con un --tag <developer-name>
- Todas las versiones deben ser únicas, no puede existir dos versiones x.x.x-1 con diferentes tags
- Las versiones deben llevar en <variante> el número del ticket actual en Jira.
- Las versiones deben llevar en <incremento> el número secuencial de los cambios en el ticket conforme se testea y desarrolla.
- Las versiones que no sean latest deben contener el tag del ambiente del proyecto donde se están probando (--tag <ambiente>) p.e. --tag develop
- Cuando se mezclan versiones de diferentes tickets en una versión para probar en testing, estas deben llamarse x.x.x-<something>.<incremento> con el tag `testing`, lo mismo cuando se prueba en staging con el tag `staging`.

## Ejemplos

- Workflow Eduardo (develop)
  - 0.0.1-1119.1 --tag develop (local)
  - 0.0.1-1119.2 --tag develop (local)
  - 0.0.1-1119.3 --tag develop (local)
  - 0.0.1-1119.4 --tag develop (local)
- Workflow Carlos (develop)
  - 0.0.1-1113.1 --tag develop (local)
  - 0.0.1-1113.2 --tag develop (local)
  - 0.0.1-1113.3 --tag develop (local)
  - 0.0.1-1113.4 --tag develop (local)
  - 0.0.1-1113.5 --tag develop (local)
- Workflow Milagros
  - 0.0.1-1200.1 --tag staging (staging)
  - 0.0.2 --tag latest
  - 0.0.2-1201.1 --tag staging (staging)
  - 0.0.2-1201.2 --tag staging (staging)
  - 0.0.3 --tag latest
  - 0.0.4 --tag latest (generado por hotfix)
- Workflow Merge Eduardo
  - 0.0.1-<something>.1 --tag testing (testing) [Se generó al hacer merge de versión 0.0.1-1119.3]
  - 0.0.1-<something>.2 --tag testing (testing) [Se generó al hacer merge de versión 0.0.1-1113.4]
  - 0.0.1-<something>.3 --tag testing (testing) [Se generó al hacer merge de versión 0.0.1-1113.4]
  - 0.0.1-<something>.4 --tag testing (testing) [Se generó al hacer merge de versión 0.0.1-1113.4]
