# Política de Privacidade — Automação ITSM

Última atualização: 31 de outubro de 2026.

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

Na versão atual, o usuário e a senha são informados no site https://relatorios-automacao-itsm.vercel.app/login-extensao. O acesso exige um segundo fator pelo Microsoft Authenticator, cadastrado por QR Code individual. O serviço processa o código temporário do aplicativo ou, quando utilizado, um código de recuperação. Após a confirmação, o site fornece um código de ativação de uso único, válido por 60 segundos e renovado enquanto a página de autorização estiver ativa, dentro do prazo de até dez minutos após o login. A extensão envia esse código, o identificador da instalação e sua versão por HTTPS ao serviço de autenticação. Ela não solicita nem armazena a senha do site ou a chave do Authenticator. Após a ativação, recebe uma credencial própria para uma sessão de 13 horas. A credencial, a identificação do usuário, da sessão e da instalação e os prazos de acesso são mantidos localmente para validar o uso e vincular as execuções ao operador.

## Uso limitado

O uso e a transferência das informações recebidas pela extensão obedecem à Política de Dados do Usuário da Chrome Web Store, incluindo os requisitos de Uso Limitado. Os dados são usados somente para fornecer ou melhorar o fluxo descrito nesta política. Eles não são vendidos, não são usados para publicidade, análise de crédito ou empréstimos e são disponibilizados aos usuários autorizados nos sistemas de destino e no painel de relatórios para executar e acompanhar o fluxo operacional solicitado. Outros acessos ficam limitados ao atendimento autorizado, à segurança e ao cumprimento de obrigações legais.

## Uso e compartilhamento

Os dados são usados somente para executar o fluxo solicitado pelo usuário. A extensão interage diretamente com os sistemas corporativos indicados no manifesto e com o Microsoft Teams usando a sessão já autenticada no navegador.

Quando a consulta de endereço é necessária, CEP ou UF, cidade e logradouro podem ser enviados diretamente ao ViaCEP para localizar e padronizar o endereço. Nos chamados Front-Office, latitude e longitude podem ser enviadas diretamente ao Nominatim/OpenStreetMap para obter o endereço aproximado. O serviço de autenticação e relatórios em https://relatorios-automacao-itsm.vercel.app recebe os dados necessários à autenticação e à sincronização. Os resultados enviados podem incluir identificadores do chamado e da execução, usuário e sessão associados, tipo e origem do fluxo, horários, duração, resultado, etapa, diagnóstico, OLT, cluster, data e hora da queda, quantidade de clientes impactados e etiquetas. Esses registros permitem acompanhar e conferir as tratativas no painel. O envio de resultados não se destina a transferir senhas dos sistemas corporativos ou imagens anexadas ao painel de relatórios.

Os destinatários dos dados são os sistemas corporativos ITSM e TOA/WFM utilizados pela organização, o Microsoft Teams/Microsoft, o ViaCEP, o Nominatim/OpenStreetMap e o serviço de autenticação e relatórios administrado pelo responsável pelo projeto. A Vercel hospeda esse serviço e processa as requisições necessárias à sua operação. A infraestrutura de hospedagem e armazenamento do painel processa os registros sob a administração do serviço. Os usuários autorizados do painel podem consultar os relatórios conforme suas permissões. A extensão não vende dados, não utiliza publicidade e não cria perfis de marketing.

## Armazenamento e retenção

O estado do fluxo, o histórico de chamados processados, os horários, as durações, os contadores e as preferências ficam armazenados localmente no perfil do Chrome. As imagens Front-Office ficam armazenadas somente durante a execução e são removidas quando a etapa do Teams é concluída ou interrompida. As configurações, histórico e filas locais permanecem até sua limpeza ou remoção da extensão. Os tokens e dados de sessão são usados até o encerramento, expiração ou revogação do acesso; encerrar a sessão não exclui automaticamente o histórico operacional. Os sistemas corporativos e o Microsoft Teams mantêm os registros enviados segundo as políticas próprias de cada organização e serviço.

Os dados de contas, sessões e relatórios também são armazenados na infraestrutura do servidor do painel. O serviço mantém os hashes das senhas, a chave individual do autenticador protegida por criptografia e os hashes dos códigos de recuperação. Os códigos de recuperação são exibidos ao usuário apenas no cadastro e cada um pode ser utilizado uma única vez. O aplicativo Microsoft Authenticator mantém os dados necessários à geração dos códigos conforme suas próprias configurações e políticas. O portal utiliza um cookie de sessão protegido para manter o acesso autenticado no navegador. A validade de 13 horas se inicia na ativação da extensão e não é renovada pelas verificações periódicas de sessão. O vencimento ou a revogação do acesso não implica a exclusão automática de dados da conta ou de registros de autenticação. Os registros operacionais não são apagados ao desinstalar a extensão ou sair da conta e permanecem no serviço até a exclusão administrativa. Solicitações de exclusão devem ser dirigidas ao administrador responsável pelo painel. Cópias de segurança podem conservar registros conforme o ciclo de retenção do serviço e não são eliminadas pela limpeza do navegador.

## Segurança

As solicitações de autenticação e sincronização são transmitidas por HTTPS. O login com usuário, senha e segundo fator ocorre no site; a extensão utiliza o código de ativação para obter uma credencial de sessão, sem receber a senha ou a chave do autenticador. As senhas são verificadas por hashes no servidor. Os segredos do autenticador e os dados das autorizações do portal são protegidos por criptografia no servidor, e o cookie do portal utiliza as proteções HttpOnly, SameSite e Secure na publicação HTTPS. O serviço aplica limites de tentativas, verifica a validade das sessões e impede a reutilização dos códigos de ativação e recuperação já consumidos. O endereço IP da requisição é utilizado para aplicar os limites de tentativas, com um identificador derivado desse endereço nos contadores. As credenciais de sessão da extensão são mantidas no armazenamento local do perfil do Chrome e não são exibidas nas consultas de estado da interface. O acesso aos sistemas corporativos continua utilizando as sessões já autenticadas no navegador.

## Permissão de depuração

A permissão `debugger` é usada temporariamente para enviar eventos de teclado e mouse ao Microsoft Teams durante a pesquisa do canal e a criação da menção. A conexão é aberta somente nessa etapa e encerrada ao final da operação. Ela não é usada para monitorar a navegação geral do usuário.

## Controle do usuário

O usuário inicia e interrompe a automação pelo painel da extensão. Também pode sair pelo painel da extensão ou pela página de autorização, remover os dados locais pelas configurações do Chrome ou desinstalar a extensão. Ao completar 13 horas, é necessário realizar novo login no site com o segundo fator e obter outro código de ativação. O administrador pode encerrar sessões, bloquear o operador, gerar uma nova senha ou redefinir o autenticador. A redefinição do autenticador invalida o cadastro anterior e seus códigos de recuperação, exigindo um novo cadastro no aplicativo. Essas ações não apagam os dados já enviados aos serviços. Para solicitar acesso, correção ou exclusão de dados da conta e dos relatórios, procure o administrador que forneceu seu acesso ao painel. Registros nos sistemas corporativos e no Teams devem ser tratados com os respectivos administradores.

## Contato

O responsável pelo projeto Automação ITSM mantém este canal de contato: [repositório do projeto](https://github.com/Lucio08/Automacao-ITSM-Site/issues). Para dúvidas ou solicitações de privacidade, peça orientação por esse canal ou diretamente ao administrador que forneceu seu acesso. Como as solicitações no GitHub são públicas, não publique senhas, tokens, dados pessoais ou conteúdo de chamados; utilize o canal apenas para pedir um meio de atendimento reservado.

