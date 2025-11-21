# AzureFrontierGirls-Challenge
<h1>PhishDetect AI</h1>
PhishDetect AI é um agente  voltado a detecção autómatica de possiveis emails suspeitos no meio corporativo, com foco na identificação de possíveis tentativas de phishing. Ele examina o contéudo da mensagem, observando urgência excessiva, erros gramaticais, tom emocional incomum, pedidos inadequados e links ou domínios diferentes do remetente declarado. <br>
A partir dessa análise, o agente gera uma avaliação objetiva do risco, expressa em porcentagem, explica quais fatores contribuiram para essa avaliação e recomenda ações de prevenção. <br>
  Quando a probabilidade de phishing ultrapassa 50%, o agente oferece ao usuario a abertura de um alerta ao setor de TI, oferecendo automaticamente uma frase pronta para encaminhamento, informando o nome do usuário e o e-mail que recebeu a mensagem suspeita e encaminhando o corpo completo do e-mail analisado,facilitando a investigação pelo time de segurança.
  <br>
<div>
 <h2> Objetivos</h2>
O PhishDetect AI tem como objetivo auxiliar na mitigação de tentativas de phishing dentro de empresas. Ele:
 <ul>
<li>Analisa o conteúdo textual do e-mail (urgência, erros, links suspeitos, tom emocional).</li>
<li>Retorna uma porcentagem de probabilidade de phishing.</li>
<li>Explica os fatores que levaram à classificação.</li>
<li>Gera recomendações de segurança.</li>
<li>Facilita o encaminhamento para o setor de TI quando necessário.</li>
</ul>
 
<br>
 <h2>Funcionalidade principais:</h2>
<li> Classificação de risco em porcentagem( ex.: 87% - Possível phishing)</li>
<li>Raciocínio resumido do que causou a pontuação( ex.: “ domínio estranho + pedido de credenciais + Senso de urgência”)</li>
<li>Identificação de links/domínios suspeitos e marcação deles</li>
<li>Interface mínima para colar texto do e-mail e ver resultado </li>
<li>Oferecer o encaminhamento automático para o departamento de TI, caso uma alta porcentagem de risco</li>
<li>Pergunta automática ao usuário sobre envio ao TI quando o risco é alto</li>
<li>Geração de alerta estruturado para o setor de TI, incluindo nome, e-mail e corpo da mensagem suspeita</li>
<li>Interface simples para colar texto do e-mail e receber a análise</li>
<br>
</div>
<h2> Entrada e saída</h2>
Entrada:
<ul><li>Texto do e-mail (remetente, assunto, corpo).</li></ul>
Saída:
<ul><li>Percentual de risco + fatores + recomendações.</li>
<li>(Opcional) Geração da mensagem para o TI caso o usuário aceite.</li></ul>
<h2>Configuração do Ambiente</h2>
<h3>Modelo utilizado</h3>
  GPT-4o Mini, escolhido por:
<ul>
<li>baixo custo</li>
<li>boa velocidade</li>
<li>disponibilidade estável na região East US 2.</li>
</ul>
<h3>Tipo de implantação</h3>
Global Standard
<h2>Instrução do Agente (Prompt do Sistema)</h2>
“Você é um agente que analisa e-mails suspeitos. Sempre avalie o e-mail recebido, gere uma porcentagem de risco entre 0% e 100%, avaliando sinais de phishing como urgência, erros gramaticais, linguagem emocional exagerada, pedidos incomuns de ação, links suspeitos ou inconsistentes com o domínio do remetente. Explique rapidamente o motivo da pontuação e dê recomendações de segurança.
Se o risco for maior que 50%, pergunte ao usuário se ele deseja encaminhar ao TI.
Se o usuário disser que sim, peça o nome completo e o e-mail. Depois gere:
<i>“[nome] ([e-mail]) recebeu um possível phishing de [remetente] e solicita verificação do setor de TI.”</i>
Inclua também o corpo completo do e-mail original.
Se o usuário disser que não deseja encaminhar, finalize apenas com orientações, sem gerar nenhuma mensagem externa.”
<h2>Testes realizados</h2>
<h3>Teste 1</h3>
<i>Email totalmente phishing</i>
Entrada: 
