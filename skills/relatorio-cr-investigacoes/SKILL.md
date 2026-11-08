---
name: relatorio-cr-investigacoes
description: Redige o relatório final de investigação particular da CR Investigações (Cícero Ramos, detetive particular, São Paulo) a partir do diário de campo, do registro de provas e das anotações do caso. Separa FATO, INDÍCIO e HIPÓTESE, liga cada afirmação a um registro (P01, P02...), aponta limitações e riscos legais. Use quando o usuário pedir "relatório do caso", "monta o relatório", "relatório final", "relatório de investigação", "transforma meu diário de campo em relatório", "relatório para o cliente" ou "relatório para o advogado".
---

# Relatório CR Investigações

Transforma o material bruto de um caso (diário de campo, registro de provas, anotações, conversa com o cliente) no relatório final padrão da CR Investigações, pronto para entregar ao contratante ou ao advogado dele.

## Princípios (valem para todo o relatório)

1. **Descrever, não julgar.** Escreva só o que foi visto e registrado. Nada de opinião sobre caráter, saúde, intenção ou culpa da pessoa observada.
2. **Toda afirmação tem lastro.** Cada frase da análise cita o registro que a sustenta (P01, P02...). Sem registro, a frase não entra ou vira HIPÓTESE.
3. **Separar FATO, INDÍCIO e HIPÓTESE.**
   - FATO: o que a mídia mostra e qualquer pessoa pode conferir.
   - INDÍCIO: o que o registro sugere, mas não prova.
   - HIPÓTESE: o que depende de verificação por outros meios (perícia, documento, decisão judicial).
4. **Nunca inventar.** Dado ausente vira campo `[preencher]` ou pergunta ao usuário. Não invente datas, horários, nomes, placas, pesos, artigos de lei ou números.
5. **Imagem não é laudo.** O relatório não conclui sobre capacidade física, doença ou diagnóstico. Escreva "não foi percebida dificuldade aparente", nunca "a pessoa está apta".
6. **Português do Brasil, objetivo.** Frases curtas, voz ativa, sujeito explícito, datas no formato dd/mm/aaaa e horas no formato hh:mm. Se a skill `portugues-tecnico-controlado` estiver disponível, aplique as regras dela. Não use a skill `humanizer` neste documento.

## Passo 1 — Conferir o material recebido

Antes de redigir, confira se há:

- Dados do caso: número (CR-AAAA-NNN), contratante, período, local, pacote contratado.
- Objetivo: a pergunta que a investigação responde e a finalidade declarada pelo cliente.
- Diário de campo: data, início, fim, local, ocorrências e registros de cada dia.
- Registro de provas: número, nome do arquivo, data e hora, local, o que mostra.

Se faltar algo essencial, liste o que falta em até 5 itens e pergunte. Se faltar só detalhe, siga com `[preencher]`.

## Passo 2 — Checagem legal (obrigatória)

Leia o material procurando sinais de obtenção ilícita:

- interceptação de ligação ou mensagem;
- acesso a celular, computador, e-mail ou rede social de terceiro;
- rastreador ou escuta em bem de terceiro;
- entrada em imóvel ou área privada sem autorização;
- uso de identidade falsa.

Se encontrar algum, **pare e avise o usuário antes de redigir**: diga qual registro tem o problema, que provas obtidas por meios ilícitos são inadmissíveis no processo (CF, art. 5º, LVI) e que podem gerar responsabilidade para o detetive e para o contratante. Sugira retirar o registro do relatório. Não cite outros artigos de lei sem ter certeza do número e do texto.

## Passo 3 — Redigir na estrutura padrão

Use exatamente estas seções, nesta ordem. O modelo completo, com tabelas, está em `references/modelo-relatorio.md`.

1. **Identificação**: tabela com número, contratada, contratante, contrato, pessoa observada (só iniciais), local, período e data de entrega. Abaixo, a frase de sigilo.
2. **Objetivo**: a pergunta e a finalidade declarada.
3. **Resumo dos resultados**: a resposta à pergunta em até 4 linhas, citando os registros principais, e a tabela de indicadores (dias, horas, saídas, registros relevantes).
4. **Metodologia e limites legais**: técnicas usadas, observação a partir de local público, equipamentos e a lista do que **não** foi usado.
5. **Diligências realizadas**: tabela dia a dia, incluindo os dias sem movimentação, e a linha de total de horas.
6. **Registros e provas**: tabela com número, arquivo, data e hora, local, descrição objetiva e código de verificação SHA-256.
7. **Análise**: três blocos (FATO, INDÍCIO e HIPÓTESE), cada item citando os registros.
8. **Limitações e considerações finais**: horas cobertas, obstáculos (visão bloqueada, pouca movimentação), a frase "Este relatório descreve o que foi observado. Não é laudo médico, perícia técnica ou conclusão jurídica." e recomendações, se houver.
9. **Declaração e assinatura**: declaração de licitude e originalidade das mídias, local e data, assinatura de Cícero Ramos, contatos e lista de anexos (A: fotos selecionadas; B: lista de arquivos com SHA-256; C: mídias originais; recibo de entrega).

## Passo 4 — Revisão antes de entregar

Confira e corrija antes de apresentar o texto:

- [ ] Toda frase da Análise cita pelo menos um registro.
- [ ] Nenhum adjetivo de julgamento ("suspeito", "mentiroso", "claramente", "obviamente").
- [ ] Nenhuma conclusão médica ou jurídica.
- [ ] Total de horas da seção 5 confere com a soma das linhas.
- [ ] Datas e horas no mesmo formato em todo o texto.
- [ ] Pessoa observada identificada só por iniciais.
- [ ] Campos ausentes marcados `[preencher]`, nunca inventados.

## Formato de saída

- Se houver ferramenta de documento editável (Claude Docs, Word ou PDF), gere o relatório nela. Se não houver, entregue em Markdown com as tabelas.
- Depois do relatório, escreva em até 5 linhas: campos `[preencher]` pendentes, alertas legais encontrados e próximo passo sugerido (por exemplo, gerar os códigos SHA-256 ou preservar provas digitais por ata notarial).

## Código de verificação SHA-256 (para orientar o usuário)

Gere o código no computador onde estão os arquivos originais:

- Windows (Prompt de Comando): `certutil -hashfile NOME_DO_ARQUIVO SHA256`
- Mac ou Linux (Terminal): `shasum -a 256 NOME_DO_ARQUIVO`

Copie o código para a tabela da seção 6 e para o Anexo B. Qualquer alteração no arquivo muda o código.

## Entrega

Entregar em PDF, pessoalmente ou em arquivo protegido por senha. Nunca pelo WhatsApp: o aplicativo comprime as mídias e apaga os metadados.
