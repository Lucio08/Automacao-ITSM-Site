# Política de Privacidade — Automação ITSM

Última atualização: 29 de outubro de 2026.

## Finalidade

A extensão Automação ITSM automatiza um fluxo operacional autorizado entre as páginas corporativas do ITSM, TOA/WFM e Microsoft Teams. Ela lê os dados necessários do chamado, preenche os formulários relacionados, publica a mensagem no canal correspondente e registra o resultado da execução localmente e no painel de relatórios vinculado ao serviço.

## Dados processados

Durante uma execução, a extensão pode processar:

- identificador, assunto, descrição e demais dados operacionais do chamado;
- nomes, endereços, cidades, coordenadas ou contatos presentes no chamado;
- tarefa criada no TOA/WFM e canal selecionado no Microsoft Teams;
- imagens anexadas aos chamados Front-Office, mantidas temporariamente apenas para inserção no Microsoft Teams;
- estado da automação, identificadores já processados, horários, duração e contadores;
- preferência de tema do painel.

Para autenticar o acesso à extensão, são processados o usuário e a senha informados no painel, o identificador da instalação e a versão da extensão. Esses dados são enviados por HTTPS ao serviço de autenticação em https://relatorios-automacao-itsm.vercel.app. A senha não é salva no armazenamento local da extensão. O token de acesso, a identificação do usuário, da sessão e do dispositivo e os prazos da sessão são mantidos localmente para validar o acesso e vincular as execuções ao usuário.

## Uso limitado

O uso e a transferência das informações recebidas pela extensão obedecem à Política de Dados do Usuário da Chrome Web Store, incluindo os requisitos de Uso Limitado. Os dados são usados somente para fornecer ou melhorar o fluxo descrito nesta política. Eles não são vendidos, não são usados para publicidade, análise de crédito ou empréstimos e são disponibilizados aos usuários autorizados nos sistemas de destino e no painel de relatórios para executar e acompanhar o fluxo operacional solicitado. Outros acessos ficam limitados ao atendimento autorizado, à segurança e ao cumprimento de obrigações legais.

## Uso e compartilhamento

Os dados são usados somente para executar o fluxo solicitado pelo usuário. A extensão interage diretamente com os sistemas corporativos indicados no manifesto e com o Microsoft Teams usando a sessão já autenticada no navegador.

Quando a consulta de endereço é necessária, CEP ou UF, cidade e logradouro podem ser enviados diretamente ao ViaCEP para localizar e padronizar o endereço. Nos chamados Front-Office, latitude e longitude podem ser enviadas diretamente ao Nominatim/OpenStreetMap para obter o endereço aproximado. O serviço de autenticação e relatórios em https://relatorios-automacao-itsm.vercel.app recebe os dados necessários à autenticação e à sincronização. Os resultados enviados podem incluir identificadores do chamado e da execução, usuário e sessão associados, tipo e origem do fluxo, horários, duração, resultado, etapa, diagnóstico, OLT, cluster, data e hora da queda, quantidade de clientes impactados e etiquetas. Esses registros permitem acompanhar e conferir as tratativas no painel. O envio de resultados não se destina a transferir senhas dos sistemas corporativos ou imagens anexadas ao painel de relatórios.

Os destinatários dos dados são os sistemas corporativos ITSM e TOA/WFM utilizados pela organização, o Microsoft Teams/Microsoft, o ViaCEP, o Nominatim/OpenStreetMap e o serviço de autenticação e relatórios administrado pelo responsável pelo projeto. A Vercel hospeda esse serviço e processa as requisições necessárias à sua operação. A infraestrutura de hospedagem e armazenamento do painel processa os registros sob a administração do serviço. Os usuários autorizados do painel podem consultar os relatórios conforme suas permissões. A extensão não vende dados, não utiliza publicidade e não cria perfis de marketing.

## Armazenamento e retenção

O estado do fluxo, o histórico de chamados processados, os horários, as durações, os contadores e as preferências ficam armazenados localmente no perfil do Chrome. As imagens Front-Office ficam armazenadas somente durante a execução e são removidas quando a etapa do Teams é concluída ou interrompida. As configurações, histórico e filas locais permanecem até sua limpeza ou remoção da extensão. Os tokens e dados de sessão são usados até o encerramento, expiração ou revogação do acesso; encerrar a sessão não exclui automaticamente o histórico operacional. Os sistemas corporativos e o Microsoft Teams mantêm os registros enviados segundo as políticas próprias de cada organização e serviço.

Os dados de contas, sessões e relatórios também são armazenados na infraestrutura do servidor do painel. Os registros operacionais não são apagados ao desinstalar a extensão ou sair da conta e permanecem no serviço até a exclusão administrativa. Solicitações de exclusão devem ser dirigidas ao administrador responsável pelo painel. Cópias de segurança podem conservar registros conforme o ciclo de retenção do serviço e não são eliminadas pela limpeza do navegador.

## Segurança

As solicitações de autenticação e sincronização são transmitidas por HTTPS. A extensão utiliza tokens para as solicitações autenticadas ao painel. A senha digitada para esse acesso é enviada ao serviço de autenticação para validação, sem ser salva localmente pela extensão. O acesso aos sistemas corporativos utiliza as sessões já autenticadas no navegador.

## Permissão de depuração

A permissão `debugger` é usada temporariamente para enviar eventos de teclado e mouse ao Microsoft Teams durante a pesquisa do canal e a criação da menção. A conexão é aberta somente nessa etapa e encerrada ao final da operação. Ela não é usada para monitorar a navegação geral do usuário.

## Controle do usuário

O usuário inicia e interrompe a automação pelo painel da extensão. Também pode sair da conta pelo painel, remover os dados locais pelas configurações do Chrome ou desinstalar a extensão. Essas ações não apagam os dados já enviados aos serviços. Para solicitar acesso, correção ou exclusão de dados da conta e dos relatórios, procure o administrador que forneceu seu acesso ao painel. Registros nos sistemas corporativos e no Teams devem ser tratados com os respectivos administradores.

## Contato

O responsável pelo projeto Automação ITSM mantém este canal de contato: [repositório do projeto](https://github.com/Lucio08/Automacao-ITSM-Site/issues). Para dúvidas ou solicitações de privacidade, peça orientação por esse canal ou diretamente ao administrador que forneceu seu acesso. Como as solicitações no GitHub são públicas, não publique senhas, tokens, dados pessoais ou conteúdo de chamados; utilize o canal apenas para pedir um meio de atendimento reservado.

