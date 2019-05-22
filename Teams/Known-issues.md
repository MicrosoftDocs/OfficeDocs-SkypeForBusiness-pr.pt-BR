---
title: Problemas conhecidos do Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 2/25/2019
ms.topic: troubleshooting
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: marcl
localization_priority: Priority
search.appverid: MET150
description: Lista atual dos problemas conhecidos do aplicativo do cliente Microsoft Teams e experiência do administrador.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 377d86bd71947588186979f20068b9e8927ccd3d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287906"
---
# <a name="known-issues-for-microsoft-teams"></a>Problemas conhecidos do Microsoft Teams

Este artigo lista os problemas conhecidos do Microsoft Teams, por área de recurso.

## <a name="administration"></a>Administração

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|    
|:-----|:-----|:-----|:-----|
|Departamento de Conta de Recursos configurado incorretamente <br/> |Contas de recursos associadas a um atendedor automático ou filas de chamadas criadas antes de janeiro de 2019 podem não ter o parâmetro Departmento configurado corretamente, o que pode fazer com que uma atribuição de número de telefone falhe. Uma correção está sendo criada para resolver esse problema. <br/> |Para atenuar esse problema, você pode executar o seguinte cmdlet para configurar o parâmetro de departamento. Set-MsolUser -ObjectId <Resource Account Object ID> -Department "Instância do aplicativo de comunicação da Microsoft" <br/> |08/05/19 <br/> |




|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Os logs de auditoria poderão relatar um nome de usuário incorreto como iniciador quando alguém tiver sido removido de uma equipe  <br/> |A equipe do Microsoft Teams é um grupo moderno no AAD. Quando você adiciona/remove um membro por meio da interface do usuário do Teams, o fluxo sabe exatamente qual usuário iniciou a alteração e o log de auditoria reflete as informações corretas. No entanto, se um usuário adicionar/remover um membro por meio do AAD, a alteração será sincronizada com o back-end das equipes sem informar às equipes que iniciaram a ação. O Microsoft Teams seleciona o primeiro proprietário da equipe como o iniciador, que também é refletido no log de Auditoria.    <br/> |  <br/> |11/05/2018  <br/> |

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|A política de EAF no EMET (Kit de Ferramentas Avançado de Experiência de Redução) pode identificar incorretamente as otimizações da área restrita do Chromium como ameaças. <br/> |Há um problema com a área restrita do Chromium no qual a política de EAF (Filtragem de Acesso à Tabela de Endereços de Exportação) no EMET (Kit de Ferramentas Avançado de Experiência de Redução) e no ATP pode identificar incorretamente as otimizações de área restrita do Chromium como ameaças. Isso faz com que o Microsoft Teams não funcione corretamente.  <br/> | Para contornar esse problema, desative o EAF para o Microsoft Teams. Você pode ler mais sobre o assunto em [Diretrizes de mitigação de EMET](https://support.microsoft.com/pt-BR/help/2909257/emet-mitigations-guidelines) Para obter mais informações sobre a política de ATP e EAF do Windows Defender, veja [Personalizar a proteção contra explorações](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/customize-exploit-protection) <br/> |11/10/2018 <br/> |

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Não é possível adicionar membros a equipes quando UsersPermissionToReadOtherUsersEnabled está definido como falso  <br/> |Quando esse valor é definido como falso no AAD, o cliente não consegue adicionar membros externos/internos no Microsoft Teams, e a seguinte mensagem de erro é exibida: "Não foi possível adicionar o membro. Ocorreu um problema. Tente novamente mais tarde." No entanto, os membros podem ser adicionados diretamente aos grupos do Office 365.    <br/> |Altere essa configuração para verdadeira no AAD.  <br/> |10/04/18  <br/> |

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|O gerenciamento de administração dos Conectores de todo o locatário não está mais disponível  <br/> |Ao tentar adicionar um conector na versão de cliente e online, ocorre o erro: Erro inesperado. Tente novamente. Set-OrganizationConfig -ConnectorsEnabled=True   <br/> |Desabilite com as configurações do Microsoft Teams. Veja este artigo de suporte: https://answers.microsoft.com/en-us/msoffice/forum/msoffice_o365admin-mso_teams-mso_o365b/how-to-enable-or-disable-connectors-in-office-365/33d4b2c1-00eb-420a-ad83-01a2b42ad098    <br/> |21/06/17  <br/> |

## <a name="apps"></a>Aplicativos

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|O [Acesso Condicional](https://docs.microsoft.com/pt-BR/azure/active-directory/conditional-access/overview) pode não funcionar ao usar a guia "Site" no aplicativo da área de trabalho<br/> |Se um site, como um portal de intranet, tiver políticas de acesso condicional (como restrições de navegador ou endereço IP), esse site poderá não ser renderizado como uma guia dentro do Teams no aplicativo da área de trabalho. <br/> |Use o Teams em um navegador em vez de usar o aplicativo da área de trabalho.  <br/> |1/7/18  <br/> |

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|As opções do conector estão ausentes para algumas equipes  <br/> |Quando você clica com o botão direito em um canal, a opção Conectores não é exibida para nenhum membro da equipe.  <br/> |O criador da equipe precisa ter uma caixa de correio online; caso contrário, nenhuma opção do conector estará disponível. É esse o comportamento esperado.  <br/> |26/06/2017  <br/> |

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|O aplicativo "Tarefas" permanece visível quando desabilitado  <br/> |Quando o aplicativo "Tarefas" está desabilitado no centro de administração, ele permanece visível no cliente Microsoft Teams para usuários com uma licença EDU. Ao selecioná-lo quando desabilitado, será exibido um erro indicando: "Houve algum problema... "  <br/> |Não há solução alternativa.  <br/> |29/12/2017  <br/> |

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Não é possível excluir conectores como proprietário de equipe  <br/> |A tentativa de excluir um conector como um proprietário, que pode adicionar um conector, enquanto a opção "Allow members to create, update, and remove connectors" (Permitir que os membros criem, atualizem e removam conectores) está desabilitada, gera um erro que indica que o usuário não tem permissão para fazer isso. <br/> |Habilitar temporariamente "Allow members to create, update, and remove connectors" (Permitir que os membros criem, atualizem e removam conectores) permitirá que o proprietário exclua o conector.  <br/> |27/07/2018  <br/> |

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

## <a name="authentication"></a>Autenticação

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Ao tentar ingressar no Teams usando o Internet Explorer ou o Edge, o programa entra em loop e falha consistentemente e não entra.   <br/> | Sua organização usa Sites Confiáveis no Internet Explorer e o aplicativo baseado na Web do Teams não se conecta porque sites confiáveis não são permitidos para o Teams. <br/>|Faça as seguintes alterações nas configurações do IE ou no Painel de Controle, usando direitos de Administrador ou um Objeto de Política de Grupo:<br/><ol><li>Em **Opções da Internet** &gt; **Privacidade** &gt; **Avançado**, aceite cookies Internos e de Terceiros e marque a caixa **Sempre permitir cookies de sessão**.</li><li>Clique em **Opções da Internet** &gt; **Segurança** &gt; **Sites Confiáveis** &gt; **Sites** e adicione todos os seguintes sites:<ul><li>https://login.microsoftonline.com</li><li>https://\*.teams.microsoft.com</li></ul></li></ol><br/><b>OBSERVAÇÃO</b>: Sempre valide e permita todas as URLs confiáveis para o Teams e os requisitos do seguinte documento: [URLs e intervalos de endereços IP do Office 365](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).   <br/> |01/11/2017  <br/> |

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Limitações no complemento do Outlook  <br/> |Para usar o complemento do Outlook, você precisa fazer login no Teams usando a autenticação multifator (MFA). Se a MFA falhar no meio do processo de login, você ainda poderá fazer login no Teams, mas você receberá uma mensagem de erro quando tentar usar o complemento.  <br/> Até o momento, o complemento só está disponível para usuários do Windows.  <br/> O complemento não funcionará se você estiver usando uma autenticação de proxy.  <br/> | Não há solução alternativa. <br/> |02/08/2017  <br/> |

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|O Microsoft Teams sempre fará login na conta do computador associada ao domínio.   <br/> |Se um usuário tiver duas contas do Microsoft Teams diferentes e tiver um computador associado ao domínio, o Microsoft Teams usará o perfil associado ao domínio no computador para conectar automaticamente o usuário ao Microsoft Teams. Para mudar para a outra conta do Teams, o usuário deve fazer logoff do aplicativo manualmente e inserir as credenciais da segunda conta para fazer logon. Se o usuário fizer logoff do Teams e reiniciar o computador, ao reiniciar, o Teams fará logon automaticamente usando o perfil associado ao domínio. <br/> | Não há solução alternativa. <br/> |02/08/2017  <br/> |

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

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|O Wiki não é criado para canais criados por convidados  <br/> |Quando um convidado cria um novo canal, a guia **Wiki** não é criada. Não existe forma de anexar manualmente a guia **Wiki** ao canal. <br/> |Não há solução alternativa.  <br/> |20/09/2017  <br/>|

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

## <a name="mobile"></a>Mobile

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Não é possível ver os canais adicionados a Favoritos automaticamente  <br/> |Alguns membros não conseguem ver os canais adicionados a Favoritos automaticamente no aplicativo móvel.  <br/> |Os membros devem entrar no aplicativo Web ou para desktop para ver os canais adicionados a Favoritos automaticamente no aplicativo móvel.  <br/> |30/04/2018  <br/>|

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Os usuários podem não conseguir alternar entre contas em dispositivos móveis gerenciados pelo Intune  <br/> |Os usuários podem não conseguir alternar entre contas em dispositivos móveis gerenciados pelo Intune.  <br/> |Não há solução alternativa.  <br/> |20/09/2017  <br/>|

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Não é possível usar o seletor divertido, Giphys ou figurinhas no aplicativo móvel  <br/> |Você não pode usar gifs, emojis ou figurinhas nos clientes móveis.  <br/> |Não há solução alternativa.  <br/> |13/03/2017  <br/> |

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Diferenças de layout entre os clientes móveis do Microsoft Teams  <br/> |As equipes são listadas em ordem alfabética, e os canais não podem ser recolhidos no cliente móvel.  <br/> |Não há solução alternativa.  <br/> |13/03/2017  <br/>|


## <a name="people"></a>Pessoas

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Fotos de perfil de usuário  <br/> | No momento, o Microsoft Teams não tem um mecanismo para impedir que os usuários alterem fotos. A equipe do BTS reuniu-se com a equipe de desenvolvimento, que apresentou o seguinte para consideração: Recurso 108874: Política de TI para desabilitar o upload de Foto de Perfil   <br/> | Se você tiver clientes que gostariam de evitar o upload de Foto de Perfil no Microsoft Teams, peça que eles votem e adicionem seu caso comercial aos comentários aqui: https://microsoftteams.uservoice.com/forums/555103-public/suggestions/18600505-disable-user-ability-to-change-profile-photos <br/> |01/03/2017 <br/> |

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
|Guia do OneNote herdada  <br/> |Guias do OneNote herdadas criadas durante a visualização pública do Microsoft Teams não podem ser renomeadas nem excluídas.  <br/> |Não há solução alternativa. <br/> |8/11/2017  <br/> |

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Função de pesquisa na guia de lista do SharePoint  <br/> |A tentativa de abrir um arquivo da função de pesquisa da guia de lista do SharePoint acionará uma solicitação de “Será necessário um novo aplicativo para abrir essa sobre”, e o arquivo não será aberto. <br/> |Abrir diretamente na lista em vez de na barra de pesquisa. <br/> |11/02/2019  <br/> |

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Falha ao baixar arquivos <br/> |Tentar baixar um arquivo quando o caminho do arquivo contiver um apóstrofo resultará na falha "O arquivo não foi baixado" ao usar o cliente da área de trabalho do Microsoft Teams. <br/> |Baixe o arquivo a partir do cliente da Web ou do SharePoint Online <br/> |10/05/2019  <br/> |

## <a name="teams"></a>Teams

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Os logs de auditoria poderão relatar um nome de usuário incorreto como iniciador quando alguém tiver sido removido de uma equipe  <br/> |A equipe do Microsoft Teams é um grupo moderno no AAD. Quando você adiciona/remove um membro por meio da interface do usuário do Teams, o fluxo sabe exatamente qual usuário iniciou a alteração e o log de auditoria reflete as informações corretas. No entanto, se um usuário adicionar/remover um membro por meio do AAD, a alteração será sincronizada com o back-end das equipes sem informar às equipes que iniciaram a ação. O Microsoft Teams seleciona o primeiro proprietário da equipe como o iniciador, que também é refletido no log de Auditoria.    <br/> |  <br/> |11/05/2018  <br/> |

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
|O nome de uma equipe com o símbolo &amp; interrompe a funcionalidade do conector  <br/> |Quando o nome de uma equipe é criado com o símbolo &amp;, os conectores dentro da equipe/grupo não podem ser estabelecidos.  <br/> |Não use caracteres especiais no nome de equipes.  <br/> |21/06/17  <br/> |

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
|Não é possível mover, excluir ou renomear arquivos após a edição  <br/> |Após um arquivo ser editado no Teams, ele não pode ser movido, renomeado ou excluído imediatamente <br/> |Atualmente, esse é um problema conhecido e a solução alternativa é aguardar algum tempo antes de fazer uma alteração administrativa.  <br/> |12/03/19  <br/> |
