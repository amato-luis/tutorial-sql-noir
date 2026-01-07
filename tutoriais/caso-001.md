# 🕵️‍♂️ Caso #001: O Mistério da Maleta no Blue Note Lounge

> **Status da Investigação:** Parte 1 e 2 Concluídas ✅
>
> **Reconhecimento:** Projeto validado e compartilhado por **Hristo Bogoev**, criador do [SQL Noir](https://sqlnoir.com).
>
> **Conceitos Técnicos:** SELECT, WHERE, LIKE, Performance em Big Data e SQL Style Guide.

---

## 📖 O Cenário: Investigação nos Anos 80

Uma maleta contendo documentos confidenciais desapareceu do famoso **Blue Note Lounge**. Testemunhas relatam um homem de sobretudo fugindo pela noite sombria. Nossa missão é atuar como detetives de dados para filtrar as evidências e identificar o suspeito.

---

## 🧠 Fase 1: A Mentalidade Estratégica (Tech Lead Mindset)

Muitos iniciantes começariam a investigação executando um `SELECT * FROM crime_scene`. No entanto, em um ambiente de **Big Data** (Interpol, CIA, PF), essa é uma falha estratégica que compromete a performance e gera custos desnecessários.

### ❌ Por que evitar o SELECT * em Produção?

1. **Custo Financeiro ($):** Em ferramentas de Cloud (como BigQuery ou AWS Athena), a cobrança é feita pelo volume de dados lidos.
2. **Performance & Banda:** Processar colunas irrelevantes desperdiça recursos de processamento e largura de banda.
3. **Robustez do Código:** Alterações no esquema da tabela podem quebrar visualizações e análises dependentes da ordem dos campos.
4. **Governança:** Dificulta a auditoria e o controle de acesso a dados sensíveis.

---

## 🛠️ Fase 2: A Query Defensiva

Para avançar no **Objetivo 1**, aplicamos uma **Query Defensiva**. Seguindo as melhores práticas do [SQL Style Guide de Simon Holywell](https://www.sqlstyle.guide/), estruturamos nossa consulta para ser clara e profissional.

### A Investigação

```
sql
SELECT 
    id, 
    date, 
    type, 
    location, 
    description
FROM 
    crime_scene
WHERE 
    location LIKE '%Blue%Note%'
    AND date LIKE '198%____'
LIMIT 1000;
```

### 💡 Pista Chave Encontrada:

Após a execução, obtivemos o relatório oficial:

> "Uma maleta contendo documentos confidenciais desapareceu. Uma testemunha reportou que um homem de sobretudo com uma cicatriz na bochecha esquerda estava fugindo da cena."

---

### 🎯 Conclusão e Próximos Passos

Com a descrição física do suspeito em mãos (**homem, sobretudo, cicatriz na bochecha esquerda**), nosso próximo objetivo técnico é cruzar esses dados com as tabelas de `suspects` e `interviews`.

**Habilidades demonstradas neste caso:**

- [x] Mapeamento de Schema e tabelas de evidências.
- [x] Aplicação de filtros de texto com operadores `LIKE`.
- [x] Controle de volume de dados com `LIMIT`.
- [x] Escrita de código limpo (Clean Code) seguindo padrões globais.

---
*Este tutorial é uma iniciativa de Luís Amato para democratizar o ensino de SQL através da gamificação.*
