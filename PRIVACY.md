# Política de Privacidade — Automação ITSM

Última atualização: 5 de setembro de 2026.

## Finalidade

A extensão Automação ITSM automatiza um fluxo operacional autorizado entre as páginas corporativas do ITSM, TOA/WFM e Microsoft Teams. Ela lê os dados necessários do chamado, preenche os formulários relacionados, publica a mensagem no canal correspondente e registra localmente o resultado da execução.

## Dados processados

Durante uma execução, a extensão pode processar:

- identificador, assunto, descrição e demais dados operacionais do chamado;
- nomes, endereços, cidades, coordenadas ou contatos presentes no chamado;
- tarefa criada no TOA/WFM e canal selecionado no Microsoft Teams;
- estado da automação, identificadores já processados, horários, duração e contadores;
- preferência de tema do painel.

A extensão não coleta senhas nem envia credenciais ao desenvolvedor.

## Uso limitado

O uso e a transferência das informações recebidas pela extensão obedecem à Política de Dados do Usuário da Chrome Web Store, incluindo os requisitos de Uso Limitado. Os dados são usados somente para fornecer ou melhorar o fluxo descrito nesta política. Eles não são vendidos, não são usados para publicidade, análise de crédito ou empréstimos e não são disponibilizados para leitura humana, exceto com consentimento específico do usuário, por motivo de segurança, para cumprir a legislação aplicável ou de forma agregada e anonimizada em operações internas.

## Uso e compartilhamento

Os dados são usados somente para executar o fluxo solicitado pelo usuário. A extensão interage diretamente com os sistemas corporativos indicados no manifesto e com o Microsoft Teams usando a sessão já autenticada no navegador.

Quando a consulta de endereço é necessária, UF, cidade e logradouro são enviados diretamente ao serviço ViaCEP para localizar e padronizar o endereço. A extensão não envia os dados a servidores próprios do desenvolvedor, não vende dados, não utiliza publicidade e não cria perfis para marketing.

## Armazenamento e retenção

O estado do fluxo, o histórico de chamados processados, os horários, as durações, os contadores e as preferências ficam armazenados localmente no perfil do Chrome. Esses dados permanecem até que o usuário limpe os dados da extensão ou a remova. Os sistemas corporativos e o Microsoft Teams mantêm os registros enviados segundo as políticas próprias de cada organização e serviço.

## Permissão de depuração

A permissão `debugger` é usada temporariamente para enviar eventos de teclado e mouse ao Microsoft Teams durante a pesquisa do canal e a criação da menção. A conexão é aberta somente nessa etapa e encerrada ao final da operação. Ela não é usada para monitorar a navegação geral do usuário.

## Controle do usuário

O usuário inicia e interrompe a automação pelo painel da extensão. Também pode remover os dados locais pela página de configurações do Chrome ou desinstalar a extensão.

## Contato

Para dúvidas sobre esta política, abra uma solicitação no [repositório do projeto](https://github.com/Lucio08/Automacao-ITSM-Site/issues).

