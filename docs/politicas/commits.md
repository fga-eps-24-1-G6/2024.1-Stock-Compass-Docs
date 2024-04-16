# Política de Commits

## Histórico de versão

| Atividade                          | Responsável   | Data       |
|------------------------------------|---------------|------------|
| Criação do documento | João Victor | 16/04/2024 |


* Os *commits* devem ser escritos em inglês, na forma infinitiva, e ainda conter uma breve descrição
* Todo *commit* deve possuir um prefixo definindo o tipo de mudança que foi feita:
    * `feat`: para criações novas;
    * `docs`: para mudanças em documentação;
    * `refact`: para refatorações/reestruturar código existente;
    * `fix`: para consertar bugs;
    * `test`: para adicionar casos de teste

**Exemplo:**

```feat: create new component```

* Para que uma pessoa seja inclusa como contribuinte no gráfico de *commits* do GitHub, basta incluir a instrução ```Co-authored-By:``` na mensagem:

**Exemplo:**

```
feat: create new component


Co-authored-By: Lucas Felipe <lucasfs1007@gmail.com>
```
