## Stacks básicas:

- Python + Pandas

- Jupyter Notebook

- SQL + DuckDB

- Plotly ou Matplotlib

- GitHub para versionamento

## Ambiente

As dependências ficam em `requirements.txt`, com versões fixadas:

| Área | Bibliotecas |
|---|---|
| Dados | pandas, numpy, pyarrow (Parquet e troca de dados com o DuckDB) |
| SQL | duckdb |
| Notebooks | jupyterlab, ipykernel, nbformat (necessário para o Plotly renderizar no notebook) |
| Visualização | matplotlib, plotly |

### Instalação

Com o [uv](https://docs.astral.sh/uv/):

```bash
uv venv
uv pip install -r requirements.txt
```

Ou com pip puro:

```bash
python3 -m venv .venv
.venv/bin/pip install -r requirements.txt
```

### Uso

```bash
source .venv/bin/activate
jupyter lab
```

### O que não vai para o git

O `.gitignore` deixa de fora o `.venv`, caches do Python e do Jupyter, bancos `*.duckdb`, arquivos `.env` e lixo de sistema/editor.

O conteúdo de `datasets/raw/` e `datasets/processed/` também é ignorado, porque microdados como PNAD e RAIS são grandes demais para o GitHub. Só os `README.md` e os `.gitkeep` dessas pastas são versionados. Para versionar um dataset pequeno, adicione uma exceção (`!caminho/do/arquivo`) no `.gitignore`.

## Regras importantes para análises:

- Correlação não é causalidade. Duas coisas acontecerem juntas não significa que uma provocou a outra.

- Cuidado com médias. Uma média salarial pode esconder desigualdades enormes.

- Considerar inflação. Salário nominal não representa necessariamente ganho real.

- Observar a metodologia. A PNAD é uma pesquisa amostral e seus pesos precisam ser considerados. A RAIS cobre o emprego formal, não todo o mercado de trabalho. 

- Não escolher apenas dados que confirmam minha opinião. Se a hipótese estiver errada, isso também pode render um episódio interessante.
