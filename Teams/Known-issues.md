---
title: Problemas conhecidos do Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: troubleshooting
ms.service: msteams
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: marcl
audience: admin
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
description: Lista atual dos problemas conhecidos do aplicativo do cliente Microsoft Teams e experiência do administrador.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2a8775722daa5cd6fc236933fc0e0fd8bad1213a
ms.sourcegitcommit: 56ceda54ca48d2984298d4d1f26017c0147d4431
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/14/2020
ms.locfileid: "43505528"
---
# <a name="known-issues-for-microsoft-teams"></a>Problemas conhecidos do Microsoft Teams

Este artigo lista os problemas conhecidos do Microsoft Teams, por área de recurso.

## <a name="common-issues-and-resolutions"></a>Problemas e soluções comuns

> [!NOTE]
> Se você precisar de ajuda para implantar o Teams para dar suporte a funcionários remotos (WFH) devido ao COVID-19, examine [Dar suporte a funcionários remotos usando o Teams](support-remote-work-with-teams.md). Além disso, você pode estar qualificado para obter assistência na implantação do programa Microsoft 365 FastTrack: visite o [Centro FastTrack](https://www.microsoft.com/fasttrack) para enviar uma solicitação.

### <a name="for-all-teams-customers"></a>Para todos os clientes do Teams

| |  |
|---------|---------|
|**Novo usuário do Teams?**    |Confira [Introdução ao Microsoft Teams](get-started-with-teams-quick-start.md).         |
|**Habilitar o acesso para convidados do Teams**     |Examine a [lista de verificação de acesso para convidado do Team](guest-access-checklist.md) e verifique se todas as etapas foram concluídas. Consulte os seguintes recursos adicionais:<ul><li>[Entendendo o Acesso para Convidados no Microsoft Teams](guest-access.md)</li>[Como um convidado ingressa em uma equipe](guest-joins.md) <li>[Configuração – Lista de Verificação de Acesso de Convidados do Microsoft Teams](guest-access-checklist.md)</li></ul>|
|**Reuniões e conferências discadas do Teams**    |Precisa de ajuda para ativar ou configurar audioconferências no Teams? Esse usuário foi criado recentemente? Em caso afirmativo, você precisará esperar de 2 a 24 horas **para que as configurações entrem em vigor**.<br>Para verificar se o usuário tem uma licença para audioconferência e tem um número padrão de chamada tarifada:<br><ol><li>No centro de administração do Microsoft 365, acesse **Usuários ativos** e selecione o usuário.</li><li> Dependendo da versão do centro de administração, escolha **Licenças e aplicativos** ou clique em **Editar** em **Licenças do produto**.</li><li> Confirme se o usuário tem licenças selecionadas para Audioconferência, Microsoft Teams e para o Skype for Business Online (plano 2).</li><li>Em **Centros de administração**, clique em **Mostrar todos** e, em seguida, clique em **Teams**.</li><li>No centro de administração do Microsoft Teams, clique em **Portal herdado**.</li><li>No centro de administração do Skype for Business, clique em **audioconferência** e, em seguida, clique em **usuários**.</li><li>Selecione o usuário e verifique se ele tem um número padrão de chamada tarifada.</li> </ol> Para saber mais, confira [Planos de chamada do Office 365](calling-plans-for-office-365.md) ou ligue para a equipe de cobrança do Microsoft Commerce para obter ajuda sobre perguntas relacionadas a licenciamento. <br><br>Recursos adicionais:<ul><li>[Conferências e reuniões no Microsoft Teams](deploy-meetings-microsoft-teams-landing-page.md)</li><li>[Audioconferência no Office 365](audio-conferencing-in-office-365.md)</li></ul>       |
|**Licença do Teams Exploratory**     |A experiência do Microsoft Teams Exploratory permite aos usuários de sua organização que têm o Azure Active Directory (AAD) e não estejam licenciados para o Teams iniciem uma experiência exploratório do Teams. Os administradores podem ativar ou desativar esse recurso para os usuários em sua organização. O [Microsoft Commercial Cloud Trial](iw-trial-teams.md) anterior agora foi substituído pela experiência do Teams Exploratory. <br><br>Recursos adicionais:<ul><li>[Como os usuários se inscrevem na experiência do Teams Exploratory](teams-exploratory.md#how-users-sign-up-for-the-teams-exploratory-experience)</li><li>[Gerenciar a experiência do Teams Exploratory](teams-exploratory.md#manage-the-teams-exploratory-experience)</li></ul>|
|**Canais privados**    |Os canais privados do Microsoft Teams criam espaços reservado para colaboração com suas equipes. O acesso é restrito aos usuários da equipe que forem proprietários ou membros do canal privado. É possível adicionar qualquer pessoa, inclusive convidados, como membro de um canal privado, desde que já sejam membros da equipe.<br><br>Você pode usar o canal privado para limitar a colaboração àqueles que precisam de conhecimento ou se quiser facilitar a comunicação entre um grupo de pessoas atribuídas para um projeto específico, sem ter que criar uma equipe adicional para gerenciar.<br><br>Recursos adicionais:<ul><li>[Como os usuários se inscrevem na experiência do Teams Exploratory](teams-exploratory.md#how-users-sign-up-for-the-teams-exploratory-experience)</li><li>[Gerenciar a experiência do Teams Exploratory](teams-exploratory.md#manage-the-teams-exploratory-experience)</li><ul>        |
|**Políticas de reunião**|As [políticas de reunião](meeting-policies-in-teams.md) são usadas para controlar os recursos disponibilizados para os participantes de reuniões programadas pelos usuários de sua organização. Depois de criar uma política e fazer suas alterações, você pode atribuir usuários à política.         |
||**Alterar ou criar uma política de reunião**<br><br>Para alterar ou criar uma política de reunião, acesse o centro de administração do Microsoft Teams > **Reuniões** > **Políticas de reunião**. Selecione uma política na lista ou selecione **Adicionar**. Se você estiver criando uma nova política, adicione um nome e uma descrição. O nome não pode conter caracteres especiais ou ter mais de 64 caracteres. Escolha as configurações e clique em **Salvar**. Por exemplo, digamos que você tenha um grupo de usuários e queira limitar a quantidade de largura de banda que a reunião exigiria. Você criaria uma nova política personalizada chamada "Largura de banda limitada" e desativaria as seguintes configurações:<br><br>Em **Áudio e vídeo**:<ul><li>Desative a opção Permitir gravação na nuvem.</li><li>Desative a opção Permitir vídeo IP.</li></ul>Em **Compartilhamento de conteúdo**:<ul><li>Desative o modo de compartilhamento de tela.</li><li>Desative a opção Permitir quadro de comunicações.</li><li>Desative a opção Permitir anotações compartilhadas.</li></ul>Em seguida, atribua a política aos usuários.         |
| |**Atribuir uma política de reunião aos usuários**<br><br><ol><li>Na barra de navegação à esquerda do centro de administração do Microsoft Teams, vá para **Usuários** e clique no usuário.</li><li>Selecione o usuário clicando à esquerda do nome de exibição do usuário e clique em **Editar configurações**.</li><li>Em **Política de reunião**, selecione a política que você deseja atribuir e clique em **Aplicar**.</li></ol>Para atribuir uma política a vários usuários de uma só vez, confira [Editar as configurações de usuários do Teams em massa](edit-user-settings-in-bulk.md). Ou você pode fazer o seguinte:<ol><li>Na barra de navegação à esquerda do centro de administração do Microsoft Teams, vá para **Reuniões > Políticas de Reunião**.</li><li>Escolha a política clicando à esquerda do nome da política.</li><li>Selecione **Gerenciar usuários**.</li><li>No painel **Gerenciar usuários**, procure o usuário pelo nome de exibição ou pelo nome de usuário, escolha o nome e clique em **Adicionar**. Repita esta etapa para cada usuário que você deseja adicionar.</li><li>Depois de terminar de adicionar as colunas, clique em **Salvar**.</li>         |
|**Solucionar um problema de teclado de discagem ausente**     |Siga este procedimento: <ul><li>Certifique-se de que o usuário recebeu uma [licença do Teams](assign-teams-licenses.md).</li><li>Verifique se o usuário possui um [Plano de Chamadas](calling-plan-landing-page.md) atribuído.</li><li>Habilite o usuário para o [Enterprise Voice](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-users-for-enterprise-voice-online-and-phone-system-voicemail#to-enable-your-users-for-phone-system-in-office-365-voice-and-voicemail).</li></ul>      |
|**Solucionar problemas de entrada do Teams**   |Primeiro, verifique se o [serviço do Microsoft Teams está íntegro](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/servicehealth). Em seguida, verifique se há códigos de erro comuns e confira [Por que estou tendo problemas para entrar no Microsoft Teams?](https://support.office.com/article/a02f683b-61a3-4008-9447-ee60c5593b0f)  Você também pode precisar revisar os [Modelos de identidade e a autenticação no Microsoft Teams](identify-models-authentication.md).         |

### <a name="for-education-customers"></a>Para os clientes do Education

|||
|---------|---------|
|Seus usuários estão vendo “Você não sabe o que está perdendo!” mensagem.   |Lembre-se de [Habilitar o Microsoft Teams para a sua escola](https://docs.microsoft.com/microsoft-365/education/intune-edu-trial/enable-microsoft-teams). Em locatários EDU, o Teams não está habilitado por padrão; será preciso ativá-lo primeiro. <br><br>Em seguida, confira [Ensino remoto e aprendizagem no Office 365 Education](https://support.office.com/article/remote-teaching-and-learning-in-office-365-education-f651ccae-7b65-478b-8366-51bb884025c4) para saber quais são as orientações mais atualizadas sobre como configurar a sua escola, planejar a lição, atender virtualmente e compartilhar conteúdo com os alunos.<br><br>Por fim, lembre-se de conferir os slides e vídeos de treinamento de administradores de TI do Microsoft Teams e muito mais em [Treinamento de administradores do Teams](itadmin-readiness.md).        |

## <a name="administration"></a>Administração

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|A política de EAF no EMET (Kit de Ferramentas Avançado de Experiência de Redução) pode identificar incorretamente as otimizações da área restrita do Chromium como ameaças. <br/> |Há um problema com a área restrita do Chromium no qual a política de EAF (Filtragem de Acesso à Tabela de Endereços de Exportação) no EMET (Kit de Ferramentas Avançado de Experiência de Redução) e no ATP pode identificar incorretamente as otimizações de área restrita do Chromium como ameaças. Isso faz com que o Microsoft Teams não funcione corretamente.  <br/> | Para contornar esse problema, desative o EAF para o Teams. Você pode ler mais sobre o assunto em [Diretrizes de mitigação de EMET](https://support.microsoft.com/help/2909257/emet-mitigations-guidelines) Para obter mais informações sobre a política de ATP e EAF do Windows Defender, veja [Habilitar a proteção contra explorações](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/enable-exploit-protection) <br/> |11/10/2018 <br/> |

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Não é possível adicionar membros a equipes quando UsersPermissionToReadOtherUsersEnabled está definido como falso  <br/> |Quando esse valor é definido como falso no AAD, os usuários não conseguirão adicionar membros externosl/internos ao Microsoft Teams e a seguinte mensagem de erro será exibida: "não foi possível adicionar o membro. Ocorreu um problema. Tente novamente mais tarde." No entanto, membros podem ser adicionados diretamente aos grupos do Office 365.    <br/> |Altere essa configuração para verdadeira no AAD.  <br/> |10/04/18  <br/> |

## <a name="apps"></a>Aplicativos

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Os usuários do Chrome versão 80 não conseguem entrar em alguns aplicativos na plataforma da equipe.<br/>|Depois que os usuários tiverem digitado as credenciais de senha corretamente na página de entrada do aplicativo, um ciclo contínuo será iniciado no local em que o usuário não for reconhecido pelo aplicativo e redirecionado para a página de entrada do aplicativo. <br/>|Direcionar os usuários para usarem o cliente da área de trabalho das equipes. |15/11/19<br/> |

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|O [Acesso Condicional](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) pode não funcionar ao usar a guia "Site" ou "Azure DevOps" no aplicativo da área de trabalho.<br/> |Se um site, como um portal de intranet, tiver políticas de acesso condicional (como restrições de navegador ou de endereço IP ou Conformidade do dispositivo), esse site poderá não ser renderizado como uma guia dentro do Teams no aplicativo da área de trabalho. <br/> |Use o Teams em um navegador em vez de usar o aplicativo da área de trabalho.  <br/> |1/7/18  <br/> |

## <a name="audio-conferencing"></a>Audioconferência

|**Problema**|**Comportamento/Sintomas**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Chamadores PSTN com o mesmo número "De" são mostrados como o mesmo usuário na lista de reuniões.  <br/> |Quando vários chamadores PSTN ingressam em uma reunião e suas identificações de chamadas são mascaradas como um único número, eles aparecem como um único chamador na lista de participantes da reunião.  <br/> |Não há solução alternativa.  <br/> |25/09/2017  <br/> |
|O painel Informações da Reunião é ocultado de forma intermitente.  <br/> |O painel Informações da Reunião poderá não ser exibido no cliente Microsoft Teams quando os usuários estiverem tentando procurar números de telefone de ponte de conferência ou IDs de conferência.  <br/> |Confira os detalhes da reunião ou o calendário do Outlook para ver os números de telefone da conferência ou a ID da conferência.  <br/> |25/09/2017  <br/> |
|Os convites de reunião do Suplemento do Outlook mostram caracteres ilegíveis em coordenadas PSTN para localidades fora dos EUA.  <br/> |Ao agendar reuniões privadas usando o Suplemento do Outlook para o Microsoft Teams em um computador com localidades fora dos EUA, as coordenadas PSTN podem conter caracteres ilegíveis.  <br/> |Não há solução alternativa.  <br/> |25/09/2017  <br/> |
|A discagem precisa usar cinco dígitos ou mais.  <br/> |Os usuários que tentam discar de uma reunião precisam digitar cinco ou mais dígitos, embora a regra de normalização do plano de discagem esteja disponível para normalizar a discagem por dígito curto para E.164.  <br/> |Disque digitando o número DID completo ou o formato do número local em vez do número do ramal interno.  <br/> |25/09/2017  <br/> |
|O controle de discagem é ocultado de forma intermitente.  <br/> |O controle de discagem pode não estar visível no painel Informações da Reunião.  <br/> |Não há solução alternativa.  <br/> |25/09/2017  <br/> |
|A ID de conferência estática não tem suporte em reuniões do Microsoft Teams.  <br/> |Se o administrador substituir a configuração padrão de ID de conferência dinâmica para ID de conferência estática, essa configuração não entrará em vigor nas reuniões do Microsoft Teams. Veja [Usar IDs dinâmicas de Audioconferência em sua organização](/skypeforbusiness/audio-conferencing-in-office-365/using-audio-conferencing-dynamic-ids-in-your-organization.md)  <br/> |Não há solução alternativa.  <br/> |25/09/2017  <br/> |
|Coordenadas de reunião PSTN não estão disponíveis para usuários locais do Skype for Business  <br/> |Se o usuário for um usuário local do Skype for Business, com licenças do Skype for Business Online, de Audioconferência e do Microsoft Teams atribuídas, todas as reuniões agendadas usando o Microsoft Teams não incluirão as coordenadas da reunião PSTN. <br/> |Não há solução alternativa.  <br/> |01/02/2018  <br/> |
|Informações de Interoperabilidade de Vídeo na Nuvem em Reunir Agora  <br/> |Se você criar uma instância Reunir Agora de uma reunião no Microsoft Teams com uma licença do CVI existente, ela não preencherá as informações do CVI. <br/> |A recomendação é agradar a reunião para preencher essas informações.  <br/> |11/06/2019  <br/> |

## <a name="authentication"></a>Autenticação

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|O Teams precisa acessar o Google Gstatic <br/> |O Teams atualmente exige o acesso (porta TCP 443) para o serviço ssl.gstatic.com do Google para todos os usuários; tal exigência é obrigatória mesmo que você não esteja usando o Gstatic. O Teams vai remover esse requisito em breve (no começo de 2020). <br/> | Não há solução alternativa. <br/> |30/01/20  <br/> |

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Depois de alterar a senha da conta de usuário, surge a mensagem de erro: A senha foi alterada ou o servidor precisa de suas informações de entrada novamente. Isso continua ocorrendo mesmo ao usar a nova senha. <br/> | As equipes vão tratar desse problema em breve em uma correção em que estão trabalhando. <br/> | Faça o logoff e refaça o logon em credenciais incorretas. Depois de a falha ocorrer, insira as credenciais corretas. <br/> |09/01/20  <br/> |

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Ao tentar ingressar no Teams usando o Internet Explorer ou o Microsoft Edge, o programa entra em loop e falha consistentemente e não entra.
   <br/> | Sua organização usa Sites Confiáveis no Internet Explorer e o aplicativo baseado na Web do Teams não se conecta porque sites confiáveis não são permitidos para o Teams. <br/>|Faça as seguintes alterações nas configurações do IE ou no Painel de Controle, usando direitos de Administrador ou um Objeto de Política de Grupo:<br/><ol><li>Em **Opções da Internet** &gt; **Privacidade** &gt; **Avançado**, aceite cookies Internos e de Terceiros e marque a caixa **Sempre permitir cookies de sessão**.</li><li>Clique em **Opções da Internet** &gt; **Segurança** &gt; **Sites Confiáveis** &gt; **Sites** e adicione todos os seguintes sites:<ul><li>https://login.microsoftonline.com</li><li>https://\*.teams.microsoft.com</li></ul></li></ol><br/><b>OBSERVAÇÃO</b>: Sempre valide e permita todas as URLs confiáveis para o Teams e os requisitos do seguinte documento: [URLs e intervalos de endereços IP do Office 365](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).   <br/> |01/11/2017  <br/> |

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|O Microsoft Teams sempre fará login na conta do computador associada ao domínio.   <br/> |Se um usuário tiver duas contas do Microsoft Teams diferentes e tiver um computador associado ao domínio, o Microsoft Teams usará o perfil associado ao domínio no computador para conectar automaticamente o usuário ao Microsoft Teams. Para mudar para a outra conta do Teams, o usuário deve fazer logoff do aplicativo manualmente e inserir as credenciais da segunda conta para fazer logon. Se o usuário fizer logoff do Teams e reiniciar o computador, ao reiniciar, o Teams fará logon automaticamente usando o perfil associado ao domínio. <br/> | Se os usuários estiverem conectados a um computador ingressado no domínio e você não desejar que o nome de usuário seja preenchido previamente na tela de entrada do Teams, os administradores poderão definir o seguinte registro do Windows para desativar o pré-preenchimento do nome do usuário (UPN ): Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams SkipUpnPrefill(REG_DWORD) 0x00000001 (1). Observação O recurso de ignorar o preenchimento prévio do nome de usuário para nomes de usuário que terminam em ".local" ou ".corp" está ativado por padrão, portanto, você não precisa definir uma chave do registro para desativá-los. Referência https://docs.microsoft.com/microsoftteams/sign-in-teams. <br/> |02/08/2017  <br/> |

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Falha de autenticação moderna ‒ autenticação de formulários não habilitada  <br/> |Quando há uma falha inicial com a autenticação multifator, use o aplicativo web para a autenticação.  <br/> Para obter mais informações, consulte [Suporte ao parâmetro prompt=login dos Serviços de Federação do Active Directory (AD FS)](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-prompt-login).  <br/> |Verifique esta configuração: `Set -MsolDomainFederationSettings -DomainName yourdomainhere -PreferredAuthenticationProtocol WsFed -SupportsMfa $False -PromptLoginBehavior Disabled`.  <br/> |19/06/2017  <br/> |

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Planner no build com SSO (logon único) <br/> |O SSO não se aplica ao Planner. Será necessário iniciar sessão novamente sempre que você usar o Planner em cada cliente pela primeira vez.  <br/> |Não há solução alternativa. Estamos trabalhando em mais aprimoramentos de autenticação.  <br/> |28/02/2017  <br/> |

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Não é possível salvar a imagem do perfil  <br/> |Os usuários não conseguem salvar a imagem do perfil quando a Caixa de Correio do Exchange está hospedada (ou estabelecida) localmente no Exchange 2016 CU2 ou anterior.  <br/> |Não há solução alternativa.  <br/> |28/02/2017  <br/> |

## <a name="browser"></a>Navegador

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Artefatos verdes da renderização de vídeos no Chrome  <br/> |São mostrados artefatos verdes durante a exibição de vídeos ou o compartilhamento de tela em uma reunião no Chrome.  <br/> |Desabilite a configuração de aceleração de hardware no Chrome.  <br/> |03/08/2017  <br/> |

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Suporte para o cliente web do Safari  <br/> | O Teams agora está disponível para visualização no Safari 11.1+ no macOS. Durante a visualização, os usuários podem encontrar problemas relacionados à Prevenção Inteligente de Rastreamento do Safari [Problemas Conhecidos do Safari](https://go.microsoft.com/fwlink/?linkid=2062082).  <br/> | Enquanto o suporte ao navegador Safari estiver em visualização, vá para **Preferências> Privacidade**  e desmarque a configuração  **Impedir acompanhamento intersite**  . Em seguida, feche o navegador e volte para teams.microsoft.com no Safari. <br/> |02/11/2016  <br/> |


## <a name="channels"></a>Canais

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Quando um usuário sai da empresa, ele é mostrado no Microsoft Teams como "Usuário desconhecido"<br/> |Quando um usuário sai da empresa, ele é mostrado no Microsoft Teams como "Usuário desconhecido". Além disso, a guia de conversa exibe: "Usuário desconhecido adicionado à equipe". <br/> |Não há solução alternativa.  <br/> |12/09/2017  <br/> |

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Os usuários não conseguem criar novamente o nome de um canal preexistente  <br/> |Depois que o nome de um canal é criado, mesmo que seja excluído, não pode ser criado novamente. Nosso sistema mantém esses dados para cenários de proteção de informações.  <br/> |Não há solução alternativa.  <br/> |13/03/2017  <br/> |

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Renomear um canal no Microsoft Teams não renomeia a pasta correspondente no SharePoint Online  <br/> |Se um canal for renomeado no Microsoft Teams, a pasta na biblioteca de documentos do SharePoint Online correspondente à equipe não será alterada da mesma forma. O nome correto da pasta do SharePoint Online é exibido na parte superior da guia Arquivos do canal renomeado.  <br/> |Não há solução alternativa.  <br/> |13/03/2017  <br/> |

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|A visualização de URL pode não ser exibida para todas as URLs  <br/> |Algumas URLs podem não mostrar uma visualização.  Isso depende do fato de a URL original ter a capacidade de mostrar uma visualização. <br/> |Não há solução alternativa. <br/> |01/09/2018 <br/> |

## <a name="chat"></a>Chat

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|@ Menções para notificação de envio de mensagem excluída com link de canal  <br/> |Há uma limitação de notificação conhecida quando você é mencionado em uma mensagem excluída. A notificação no feed navegará para o canal, mas não para uma mensagem específica. <br/> | Por design <br/> | 28/03/2017  <br/>|


## <a name="client"></a>Cliente

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Não é possível iniciar equipes do Surface Hub na Microsoft Store |O Microsoft Teams para Surface Hub não será iniciado **quando** você clicar em Iniciar na Microsoft Store. | A inicialização dos aplicativos do Surface Hub na lista da Microsoft Store não tem suporte do Windows no Surface Hub. <br> <br/> Reinicie o Surface Hub após instalar as equipes. | 27/02/18 |

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|O Microsoft Teams não é atualizado automaticamente   <br/> | Quando o Microsoft Teams é instalado em Arquivos de Programas usando scripts de instalação em vez de ser instalado no local padrão, o cliente não é atualizado automaticamente quando novas versões estão disponíveis.    <br/> | Por design. Instale o aplicativo no local padrão: `user\Appdata`.  <br/> | 07/09/2017  <br/> |

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|O uso de Symlink ou o mapeamento de uma unidade para C:\users faz com que o aplicativo seja iniciado com uma tela em branco  <br/> | Quando o Microsoft Teams é instalado em Arquivos de Programas usando scripts de instalação em vez de ser instalado no local padrão, o cliente não é atualizado automaticamente quando novas versões estão disponíveis.   <br/> | Por design. Instale o aplicativo no local padrão: `user\Appdata`. Se o mapeamento precisar existir, você deverá usar a versão da Web do Microsoft Teams.  <br/> | 07/09/2017  <br/> |

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|O uso de Symlink ou o mapeamento de uma unidade para c:\users fará com que o aplicativo seja iniciado com uma tela em branco  <br/> |Quando o local padrão de `C:\users\<user>\appData` é alterado movendo a pasta `C:\users` ou com o uso de symlink, o aplicativo é iniciado com uma tela em branco.   <br/> |Não há solução alternativa conhecida. Se o mapeamento precisar existir, você deverá usar a versão da Web do Microsoft Teams.   <br/> |13/03/2017  <br/> |

## <a name="environment"></a>Ambiente.

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|As caixas de correio de grupos não estão habilitadas para fins de arquivamento (armazenamento extra)  <br/> |No Centro de Segurança e Conformidade do Office 365, os administradores globais não conseguem habilitar o arquivamento nas caixas de correio de grupos. Eles só conseguem em caixas de correio de usuários.  <br/> |Se a capacidade da caixa de correio do grupo estiver quase cheia, entre em contato com o Suporte do Microsoft Office para aumentar o tamanho da caixa de correio.  <br/> |01/02/2017  <br/> |

## <a name="guest-access"></a>Acesso de Convidado

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Os cliente da UE e da APAC recebem um erro quando adicionam um usuário convidado de outro locatário    <br/> | Para os clientes da UE e da APAC, ocorre um atraso na replicação entre o Microsoft Teams e o Azure Active Directory. Quando usuários de um locatário da UE ou da APAC tentam adicionar um usuário convidado de outro locatário, eles recebem uma mensagem de erro solicitando nova tentativa.   <br/> |Clique mais uma vez no botão Tentar Novamente para adicionar o usuário convidado.  <br/> |08/11/2017  <br/> |

## <a name="linux"></a>Linux

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|O AutoStart no Linux não está funcionando. <br/> |O AutoStart no Linux não inicia o aplicativo Teams. <br/> | <br/> |05/12/19  <br/>|

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Tela branca ao retomar da suspensão. <br/> |Quando o computador é retomado/despertado do modo de suspensão, pode haver uma alteração de rede (especialmente quando o computador está conectado à VPN antes de ser colocado em suspensão) e demora algum tempo para que o computador obtenha novamente a conexão. A combinação dessas coisas pode levar a uma tela branca no Teams. <br/> |Será útil reiniciar o cliente Teams.  <br/> |05/12/19  <br/>|

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Cursor ausente no compartilhamento de tela. <br/> |Ao compartilhar a tela, a outra parte não vê o cursor da pessoa que está compartilhando a tela. <br/> | <br/> |05/12/19  <br/>|

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Problema na execução em paralelo com o VMWare workstation. <br/> |O aplicativo Teams enfrenta problemas ao ser executado paralelamente com o VMWare workstation. <br/> | <br/> |05/12/19  <br/>|

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Notificações no KDE criam uma nova barra de tarefas.<br/> |Notificação no KDE criam uma nova janela na barra de tarefas. <br/> | <br/> |05/12/19  <br/>|

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Os gerenciadores de pacote não mostram a lista de alterações. <br/> |O gerenciador de pacote não mostra a lista de alterações. <br/> | <br/> |05/12/19  <br/>|

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Não é possível iniciar o cliente Teams no modo offline. <br/> |Não é possível iniciar o Teams Offline no cliente do Linux. <br/> | <br/> |05/12/19  <br/>|

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Configurações de dispositivo durante a reunião. <br/> |Quando estiver em uma reunião e alterar as configurações do dispositivo, o indicador do Microfone não registrará nada que está sendo capitado. <br/> | <br/> |05/12/19  <br/>|

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Não é possível fechar o aplicativo Teams usando o teclado. <br/> |Não é possível fechar o aplicativo Teams usando a `$mod + shift + q` padrão ou clicando no botão fechar no aplicativo. <br/> | <br/> |05/12/19  <br/>|

## <a name="meetings"></a>Reuniões

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Os usuários não podem acessar Reuniões/Conectores, mas têm caixas de correio do Exchange Online. <br/> |O cliente bloqueia ativamente o EWS de serviços no Exchange Online, mas o MS Teams precisa estar em conformidade com as políticas do EWS. <br/> |Para que o MS Teams esteja em conformidade, você deve adicionar a seguinte Cadeia de Caracteres de Agente de Usuário ao MS Teams em EWSAllowList: `SkypeSpaces/*` e `MicrosoftNinja/*`, incluindo os asteriscos. Pode ser usado o seguinte comando: `Set-organizationconfig -EwsAllowList @{Add="MicrosoftNinja/*","SkypeSpaces/*"}`<br/> Para obter mais informações, confira: https://docs.microsoft.com/powershell/module/exchange/organization/Set-OrganizationConfig?view=exchange-ps. <br/> |30/05/2017  <br/>|

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Skype for Business obrigatório para algumas reuniões  <br/> |O seu calendário de reuniões é convenientemente exibido no Microsoft Teams. Para inserir uma reunião, clique em **Entrar**. <br/> Enquanto continuamos o desenvolvimento nesta área, se esta reunião foi agendada com o Skype for Business e você clicar em **Entrar**, o Microsoft Teams iniciará seu cliente Skype for Business para concluir sua entrada na reunião. As reuniões agendadas no Microsoft Teams iniciarão diretamente no produto.  <br/> No futuro, simplificaremos essa experiência.  <br/> |Clique em **Entrar**. O Microsoft Teams decide de forma inteligente se o Skype for Business é obrigatório para o usuário entrar na reunião com base na URL incluída na descrição da reunião.  <br/> |13/03/2017  <br/> |


|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Número máximo de participantes de reuniões  <br/> |Cada reunião do Microsoft Teams pode ter até 250 participantes.  <br/> |Crie eventos ao vivo no teams que podem hospedar 10000 usuários.  <br/> |13/03/2017  <br/> |

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|As reuniões não estão disponíveis  <br/> |A funcionalidade de reunião não está disponível quando a Caixa de Correio do Exchange está hospedada (ou estabelecida) localmente em uma versão anterior ao Exchange 2016 CU3.  <br/> |Atualize para o Exchange 2016 CU3 ou posterior para implantações locais.  <br/> |28/02/2017  <br/> |

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Não há áudio durante o compartilhamento de conteúdo em uma reunião de transmissão  <br/> |Ao compartilhar conteúdo durante uma reunião de transmissão, o áudio do conteúdo compartilhado (link do YouTube ou um arquivo de vídeo salvo) não pode ser ouvido pelos participantes.  <br/> |Isso não é por design.  No momento o Microsoft Teams não dá suporte ao áudio do compartilhamento de conteúdo  <br/> |09/10/2018  <br/> |

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Não foi possível iniciar a reunião como Organizador no Outlook, pois você pode ficar preso no Lobby Virtual  <br/> |Você pode se deparar com esse problema se o seu cliente do Outlook estiver conectado a uma conta diferente do seu cliente do Teams. <br/> |Ao ingressar na reunião, certifique-se de que o cliente do Outlook e o cliente do Teams estejam conectados à mesma conta em que a reunião foi agendada.  <br/> |05/11/18  <br/> |

## <a name="mobile"></a>Mobile

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Não é possível ver os canais adicionados a Favoritos automaticamente  <br/> |Alguns membros não conseguem ver os canais adicionados a Favoritos automaticamente no aplicativo móvel.  <br/> |Os membros devem entrar no aplicativo Web ou para desktop para ver os canais adicionados a Favoritos automaticamente no aplicativo móvel.  <br/> |30/04/2018  <br/>|

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Os usuários podem não conseguir alternar entre contas em dispositivos móveis gerenciados pelo Intune  <br/> |Os usuários podem não conseguir alternar entre contas em dispositivos móveis gerenciados pelo Intune.  <br/> |Não há solução alternativa.  <br/> |20/09/2017  <br/>|

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Problemas que você pode encontrar se estiver usando iOS 13 Beta  <br/> |1. As notificações do Teams não estão sendo disparadas.  Isso inclui chats, menção e chamadas.  2. A visualização de arquivo não está funcionando com a versão beta.  <br/> |Não há nenhuma solução alternativa neste momento.  Estamos trabalhando com desenvolvedores da Apple para encontrar correções para esses problemas.  <br/> | 25/06/19  <br/>|


## <a name="people"></a>Pessoas

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Fotos de perfil de usuário  <br/> | No momento, o Microsoft Teams não tem um mecanismo para impedir que os usuários alterem fotos. A equipe do BTS reuniu-se com a equipe de desenvolvimento, que apresentou o seguinte para consideração: Recurso 108874: Política de TI para desabilitar o upload de Foto de Perfil   <br/> | Se você tiver clientes que gostariam de evitar o upload de Foto de Perfil no Microsoft Teams, peça que eles votem e adicionem seu caso comercial aos comentários aqui: https://microsoftteams.uservoice.com/forums/555103-public/suggestions/18600505-disable-user-ability-to-change-profile-photos <br/> |01/03/2017 <br/> |



## <a name="phone-system"></a>Sistema Telefônico

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Departamento de conta de recursos configurado incorretamente <br/> | Contas de recursos locais associadas a um atendedor automático ou fila de chamada criadas antes de janeiro de 2019 podem não ter o parâmetro Departamento definido corretamente, o que pode causar falha na atribuição de um número de telefone. Uma correção está em andamento para resolver esse problema. <br/><br/> Contas de recurso configuradas usando New-CsHybridApplicationEndpoint com o Skype for Business Server podem não ter o parâmetro Departamento definido corretamente, o que causará falha na criação da conta de recurso no centro de administração do Teams. Nesse caso, você precisa configurar o nome do departamento no Active Directory local antes de sincronizar com o online.|Para atenuar esse problema, você pode executar o seguinte cmdlet para definir o parâmetro Department: Set-AdUser -Identity <objectId> -Department “Microsoft Communication Application Instance” <br/> Confira também a [Atualização do atendente automático e do serviço das filas de chamadas](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521). |08/05/19 <br/> |


|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Atraso de sincronização de contas de recursos|Não é possível atribuir um número de telefone à conta de recurso ou você recebe a mensagem de erro “A seguinte instância do aplicativo não está presente no BVD”.|Permita 24 horas por sincronização. Se já tiver decorrido 24 horas, remova a atribuição do número de telefone, elimine a conta do recurso e crie uma nova com um nome diferente.|18/5/2019|

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Não é possível atribuir um número de serviço gratuito do centro de administração do Teams|Ao tentar atribuir um número de serviço gratuito no centro de administração do Teams, você recebe a mensagem de erro “Você precisa de uma licença do sistema telefônico”.|Ao invés, use cmdlets do PowerShell para atribuir um número de serviço gratuito.|18/5/2019|


|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Conta de recurso corrompida|Conta do recurso não funciona|Remover ou substituir a licença de uma conta de recurso ou criar uma nova conta de recurso com o mesmo URI do SIP como uma anteriormente excluída resultará em uma conta de recurso corrompida.|18/5/2019|


|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Número de telefone bloqueado|Número de telefone bloqueado: Excluir a conta do recurso antes de remover o número de telefone bloqueará o número de telefone.|Contate o suporte da Microsoft para liberar o número de telefone.|18/5/2019|

## <a name="provisioning"></a>Provisionamento

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Usuário do SharePoint incorreto criado para o site do Microsoft Teams SharePoint  <br/> |O criador do SharePoint para um grupo do Microsoft Teams aparece como um administrador do SharePoint, e não o usuário correto.  <br/> Ao fazer uma auditoria no console de administração do SharePoint, o criador da página de coleta de sites associado ao Grupo do Office 365 criado na equipe no Microsoft Teams é o administrador do SharePoint.  <br/> |Não há solução alternativa.  <br/> |21/07/2017  <br/> |

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Os usuários não conseguem criar uma equipe  <br/> |A sua empresa pode ter definido uma política que restringe quem pode criar grupos ou equipes no Office 365.  <br/> |Verifique com o seu administrador de TI para entender a política da sua empresa para a criação de grupos e equipes.  <br/> |13/03/2017  <br/> |

## <a name="skype-for-business-to-teams-upgrade"></a>Atualização do Skype for Business para o Microsoft Teams

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|

## <a name="tabs"></a>Guias

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Guias de site geram confusão para o cliente  <br/> |As guias de site não são equivalentes às de um navegador. Diversos sites, especialmente aqueles que exigem autenticação ou uso de pop-ups, não funcionarão quando forem exibidos como uma guia de site.  <br/> |Estamos trabalhando para melhorar a interface do usuário e torná-la mais clara para os clientes.  <br/> |02/05/2018  <br/>|

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Guias que não funcionam desde que o Acesso Condicional foi habilitado <br/> |Algumas guias podem não ser mais carregadas no Cliente de Desktop desde que o Acesso Condicional foi habilitado no locatário. As guias são carregadas ao ser usado o Cliente Web. Algumas guias que podem ser afetadas são: PowerBI, Forms, VSTS, PowerApps e Lista do SharePoint.  <br/> |Para ver as guias afetadas, você deve usar o Microsoft Teams no Microsoft Edge, no IE ou no Chrome com a extensão de Contas do Windows 10 instalada. Algumas guias ainda dependem da autenticação da Web, que não funciona no Cliente de Desktop quando o AC está habilitado. Estamos trabalhando com parceiros para habilitar esses cenários. Até agora, habilitamos o Planner, o OneNote e o Stream. <br/> |05/04/2018  <br/>|

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|A lista de espaços de trabalho não está em ordem alfabética  <br/> |Os clientes que alternarem espaços de trabalho ao adicionar uma guia do PowerBI encontrarão uma lista de espaços de trabalho fora da ordem alfabética entre os quais alternar.  <br/> |Não há solução alternativa.  <br/> |13/03/2017  <br/>|

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|A barra de rolagem desaparece ao selecionar relatórios  <br/> |Os usuários que adicionam relatórios do PowerBI não conseguem percorrer uma lista mais longa que uma tela de relatórios sem perder a barra de rolagem.  <br/> |Use as setas para cima e para baixo para percorrer a lista.  <br/> |13/03/2017  <br/>|

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Integração entre o Planner e o Microsoft Teams com o Planner online <br/> |Os buckets de tarefas no Planner não são mostrados na experiência online do Planner.  <br/> |Não há solução alternativa. <br/> |28/02/2017  <br/>|


|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Integração entre o Planner e o Microsoft Teams com o Planner online <br/> |Os proprietários não conseguem criar um plano de um grupo criado a partir de um grupo existente do Office 365.  <br/> |Forneça permissões de membro ao proprietário do grupo. <br/> |14/01/2020  <br/>|




|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Guia do OneNote herdada  <br/> |Guias do OneNote herdadas criadas durante a visualização pública do Microsoft Teams não podem ser renomeadas nem excluídas.  <br/> |Não há solução alternativa. <br/> |8/11/2017  <br/> |

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Função de pesquisa na guia de lista do SharePoint  <br/> |A tentativa de abrir um arquivo da função de pesquisa da guia de lista do SharePoint acionará uma solicitação de “Será necessário um novo aplicativo para abrir essa sobre”, e o arquivo não será aberto. <br/> |Abrir diretamente na lista em vez de na barra de pesquisa. <br/> |11/02/2019  <br/> |

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Falha ao baixar arquivos <br/> |Tentar baixar um arquivo quando o caminho do arquivo contiver um apóstrofo resultará na falha "O arquivo não foi baixado" ao usar o cliente da área de trabalho do Microsoft Teams. <br/> |Baixe o arquivo a partir do cliente da Web ou do SharePoint Online <br/> |10/05/2019  <br/> |

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Não é possível carregar ou baixar o arquivo do OneNote <br/> |Não é possível carregar ou baixar um arquivo ou bloco de anotações do OneNote usando o Microsoft Teams. <br/> |Baixar ou carregar o arquivo diretamente no SharePoint Online <br/> |07/05/2019  <br/> |

## <a name="teams"></a>Teams

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Os e-mails do correio de voz do Teams chegarão com falha de spf se for uma chamada sip, se for uma chamada pstn para um usuário, chegarão com o atributo from sem o valor correto, se o cliente tiver uma regra que analisa os correios de voz spf terão uma ação onde o etr decidirá. <br/> | <br/> | A solução alternativa de 29/08/2019 adicionará uma exceção no etr se a mensagem for uma caixa postal.


|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|O carregamento de fotos para o Teams não está bloqueado no Outlook Web App/Outlook, embora isso seja um requisito da política   <br/> | O Teams permite que os usuários carreguem fotos diretamente para o Office 365, apesar de as configurações da política em vigor impedirem o carregamento de fotos para o Outlook Web App.   <br/> |<br/>  |16/10/2017  <br/> |

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|A lista de equipes públicas não exibe todas as equipes  <br/> |A lista de equipes públicas está baseada no Microsoft Graph.  <br/> |Se você não vê uma equipe, tente pesquisá-la na caixa de pesquisa superior à direita. Além disso, os proprietários da equipe devem comunicar os nomes das equipes aos colegas, pois muitas equipes podem ser mostradas nos resultados da pesquisa. <br/> | 21/07/2017  <br/>|

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Nomes de equipe que contêm caracteres especiais podem criar erros na criação de reuniões  <br/> |O usuário receberá a mensagem **ocorreu um erro** em vermelho ao tentar criar uma reunião para uma Equipe que tenha caracteres especiais no nome.   <br/> |Renomeie ou recrie a equipe com um nome que não contenha "/".  <br/> |13/07/2017  <br/> |

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Máximo de 5000 membros de equipe  <br/> |Cada equipe do Microsoft Teams pode ter no máximo 5000 membros.  <br/> |Não há solução alternativa.  <br/> |06/02/2019  <br/> |

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|A exclusão de uma equipe também excluirá o grupo associado a ela  <br/> |Os usuários podem não perceber que o Grupo do Office 365 subjacente é excluído quando a equipe é excluída. Além disso, se o grupo do Office 365 subjacente for excluído, a equipe será excluída também.  <br/> |Idiomas adicionais no Microsoft Teams fornecem essa informação ao usuário. Essa informação não está presente na interface dos Grupos do Office 365. O suporte técnico pode recuperar um Grupo/Equipe excluído.  <br/> |13/03/2017  <br/> |

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|O aplicativo da área de trabalho do Teams mostra uma tela em branco  <br/> | <br/> |Tente excluir ou reinstalar os drivers gráficos no computador ou inicie as o Microsoft Teams por meio de uma linha de comando com um sinalizador de desabilitação de GPU:<ul><li>Para o Windows: abra o prompt de comando e insira o seguinte: `cd %localappdata%\microsoft\teams\current run Teams.exe --disable-gpu`</li><li>Para o Mac: inicie o Terminal e insira o seguinte: `cd \Applications folder Microsoft\ Teams.app/Contents/MacOS/Teams --disable-gpu`</li></ul> <br/> |<br/> |

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Usuário não recebe o email de boas-vindas quando adicionado administrativamente  <br/> |Ao adicionar um membro a uma equipe usando o PowerShell ou o Centro de administração do Teams, ele não recebe um email de boas-vindas do Microsoft Teams  <br/> |Adicionar um membro a partir da interface do usuário do Teams diretamente enviará um email. Atualmente, não há solução alternativa administrativamente.  <br/> |12/2/2019  <br/> |

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Problema de interoperabilidade entre o Symantec DLP e o Teams <br/> |Os agentes de Ponto de Extremidade da Symantec DLP podem interferir no processo do Teams, o que pode levar a uma falha de inicialização ou de saída.  <br/> |Excluir (lista aprovada) do Teams.exe dos agentes de Ponto de Extremidade da Symantec DLP, conforme descrito no <a href="https://support.symantec.com/us/en/article.TECH220322.html">Artigo de suporte da Symantec</a>. <br/> |15/07/19  <br/> |

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|A criptografia Dell impede a inicialização do Teams <br/> |A criptografia Dell (chamada anteriormente de Criptografia de Proteção de Dados da Dell) pode corromper a instalação do Teams durante o processo de atualização, levando a uma falha permanente para iniciar o aplicativo. <br/> |Exclua a pasta do Teams em %LocalAppData%\Microsoft\Teams da política de criptografia. <br/> |21/11/19  <br/> |
