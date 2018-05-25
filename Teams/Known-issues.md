---
title: Problemas conhecidos do Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 5/9/2018
ms.topic: article
ms.service: msteams
ms.reviewer: marcl, ninadara, v-leslc
description: Lista atual dos problemas conhecidos do aplicativo do cliente Microsoft Teams e experiência do administrador.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6624aa94ef6581805e3ba2b79f09aefb95616bb0
ms.sourcegitcommit: 1cb8ab7d1e3debb84f051be404403e4a116ee741
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/21/2018
---
# <a name="known-issues-for-microsoft-teams"></a>Problemas conhecidos do Microsoft Teams
  
Este artigo lista os problemas conhecidos for Microsoft Teams, pela área de recurso.
## 

## <a name="administration"></a>Administração
|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Não é possível adicionar membros a equipes quando UsersPermissionToReadOtherUsersEnabled estiver definido como false  <br/> |Quando este valor é definido como false no AAD, cliente não é capaz de adicionar membros interno/externo em Teams da Microsoft e a seguinte mensagem de erro é exibida: "não podemos não pôde adicionar membro. Executamos em um problema. Tente novamente mais tarde." No entanto, os membros podem ser adicionados diretamente para grupos do Office 365.    <br/> |Altere essa configuração como true no AAD.  <br/> |4/10/18  <br/> |

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Gerenciamento de administração dos conectores de todo o locatário não está mais disponível  <br/> |Ao tentar adicionar um conector no cliente e versão online recebemos o erro: Ocorreu um erro inesperado. Tente novamente. Set-OrganizationConfig - ConnectorsEnabled = True   <br/> |Desabilite com configurações de equipes. Consulte o artigo de suportehttps://msdn.microsoft.com/en-us/microsoft-teams/connectors  <br/> |21/06/2017  <br/> |

## <a name="apps"></a>Aplicativos
|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Opções de conector está ausente para algumas equipes  <br/> |Quando você clica com o botão direito em um canal, a opção Conectores não é exibida para nenhum membro da equipe.  <br/> |O criador da equipe precisa ter uma caixa de correio online; caso contrário, nenhuma opção do conector estará disponível. É esse o comportamento esperado.  <br/> |26/06/2017  <br/> |

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|"Atribuições" app permanece visble quando desabilitada  <br/> |Quando o aplicativo "Atribuições" está desabilitado no Centro de administração, permanece visível no cliente equipes para usuários licenciados EDU. Selecionando-o quando desabilitada retornará um erro indicando, "Doh! Algo deu errado..."  <br/> |Não há solução alternativa.  <br/> |12/29/17  <br/> |

## <a name="authentication"></a>Autenticação
|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Ao tentar ingressar no Teams usando o Internet Explorer ou o Edge, o programa entra em loop e falha consistentemente e não entra.   <br/> | Sua organização usa Sites Confiáveis no Internet Explorer e o aplicativo baseado na Web do Teams não se conecta porque sites confiáveis não são permitidos para o Teams. <br/>|Faça as seguintes alterações nas configurações do IE usando direitos de administrador ou um Objeto de Política de Grupo:<br/><ol><li>Em **Opções da Internet** &gt; **privacidade** &gt; **Avançado**, aceitar os cookies primários e de terceiros e a caixa de seleção para **sempre permitir cookies de sessão**.</li><li>Clique em **Opções da Internet** &gt; **Sites confiáveis** &gt; **Sites**e adicione todos os seguintes:<ul><li>https://\*.microsoft.com</li><li>https://\*.microsoftonline.com</li><li>https://\*.teams.skype.com</li><li>https://\*.teams.microsoft.com</li><li>https://\*.sfbassets.com</li><li>https://\*.skypeforbusiness.com</li></ul></li></ol><br/><b>OBSERVAÇÃO</b>: Sempre valide e permita todas as URLs confiáveis para o Teams e os requisitos do seguinte documento: [URLs e intervalos de endereços IP do Office 365](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams).   <br/> |01/11/2017  <br/> |

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Limitações no complemento do Outlook  <br/> |Para usar o complemento do Outlook, você precisa fazer login no Teams usando a autenticação multifator (MFA). Se a MFA falhar no meio do processo de login, você ainda poderá fazer login no Teams, mas você receberá uma mensagem de erro quando tentar usar o complemento.  <br/> Até o momento, o complemento só está disponível para usuários do Windows.  <br/> O complemento não funcionará se você estiver usando uma autenticação de proxy.  <br/> | Não há solução alternativa. <br/> |02/08/2017  <br/> |

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Microsoft Teams será sempre acesse a conta de domínio PC.   <br/> |Se um usuário possui duas contas de equipes diferentes e tiver uma máquina com domínio habilitado, equipes usará o perfil de domínio na máquina para fazer logon automaticamente o usuário em equipes. Para alternar para a outra conta de equipes, o usuário deve manualmente saia do aplicativo e insira as credenciais para a segunda conta para fazer logon. Se o usuário fizer logoff do equipes e reinicia a máquina, durante a reinicialização, equipes automaticamente efetuará login usando o perfil do domínio. <br/> | Não há solução alternativa. <br/> |02/08/2017  <br/> |

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Falha de autenticação moderno - autenticação de formulários não habilitado  <br/> |Quando há uma falha inicial com a autenticação multifator, use o aplicativo web para a autenticação.  <br/> Para obter mais informações, consulte [Suporte ao parâmetro prompt=login dos Serviços de Federação do Active Directory (AD FS)](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-prompt-login).  <br/> |Verifique esta configuração: Set -MsolDomainFederationSettings -DomainName yourdomainhere -PreferredAuthenticationProtocol WsFed -SupportsMfa $False -PromptLoginBehavior Disabled.  <br/> |19/06/2017  <br/> |

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Planejador de compilação de logon único (SSO) <br/> |O SSO não se aplica ao Planner. Será necessário iniciar sessão novamente sempre que você usar o Planner em cada cliente pela primeira vez.  <br/> |Não há solução alternativa. Estamos trabalhando em mais aprimoramentos de autenticação.  <br/> |28/02/2017  <br/> |

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Não é possível salvar a imagem de perfil  <br/> |Os usuários não conseguem salvar a imagem de perfil quando a caixa de correio do Exchange está hospedada (ou estabelecida) localmente.  <br/> |Não há solução alternativa.  <br/> |28/02/2017  <br/> |

## <a name="browser"></a>Navegador
|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Artefatos verdes do processamento de vídeos no Chrome  <br/> |Artefatos verdes aparecem enquanto exibindo vídeo ou compartilhamento de tela em uma chamada ou meetup no Chrome.  <br/> |Desabilite a configuração de aceleração de hardware no Chrome.  <br/> |03/08/2017  <br/> |

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Suporte para o cliente web do Safari  <br/> |Os usuários que tentam abrir o cliente Microsoft Teams no Safari são direcionados para baixar o cliente desktop. A Microsoft está examinando o suporte do Safari e compartilhará as atualizações por meio do [Roteiro do Microsoft Teams](http://aka.ms/TeamsRoadmap).  <br/> |Navegadores de internet, que incluem suporte para uso: Internet Explorer 11 +, Microsoft Edge 12 +, Chrome 51.0 + e Firefox 47.0 +.  <br/> |02/11/2016  <br/> |

## <a name="channels"></a>Canais
|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Quando um usuário deixa a empresa, ela será exibida na Microsoft Teams como "Usuário desconhecido"<br/> |Quando um usuário deixa a empresa, ela será exibida na Microsoft Teams como "Usuário desconhecido". Além disso, a guia de conversa exibe: "usuário desconhecido foi adicionado para a equipe." <br/> |Não há solução alternativa.  <br/> |9/12/17  <br/> |

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Os usuários não conseguem criar novamente o nome de um canal preexistente  <br/> |Depois que o nome de um canal é criado, mesmo que seja excluído, não pode ser criado novamente. Nosso sistema mantém esses dados para cenários de proteção de informações.  <br/> |Não há solução alternativa.  <br/> |13/03/2017  <br/> |

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Renomear um canal em Microsoft Teams não renomeia a pasta correspondente no SharePoint Online  <br/> |Se um canal é renomeado no Teams da Microsoft, a pasta na biblioteca de documentos do SharePoint Online correspondente para a equipe não altera para corresponder. O nome correto da pasta do SharePoint Online é exibido na parte superior da guia arquivos canal renomeado.  <br/> |Não há solução alternativa.  <br/> |13/03/2017  <br/> |

## <a name="chat"></a>Chat

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|@ Menções para mensagem excluída enviar notificação com link de canal  <br/> |Existe uma limitação conhecida notificação quando você estiver em mencionados em uma mensagem que será excluída; a notificação no feed navegarão para o canal, mas não para uma mensagem específica. <br/> | Por design <br/> | 3/28/17  <br/>|

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Os usuários do Skype for Business local não recebem minhas mensagens  <br/> |O envio de mensagens não será concluído quando os usuários do Microsoft Teams tentarem enviar uma mensagem para outro indivíduo que esteja usando o Skype for Business local.  <br/> | Existe suporte para a interoperabilidade entre o Teams e os usuários hospedados no Skype for Business Online. Os usuários do Teams podem enviar mensagens individuais 1:1 para usuários fora do Teams que usem o Skype for Business Online. <br/> Não existe suporte para a interoperabilidade entre o Teams e os usuários hospedados no Skype for Business local. Os usuários do Teams não podem enviar mensagens individuais 1:1 para usuários fora do Teams que usem o Skype for Business local.  <br/> |02/11/2016  <br/> |

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Os usuários do Skype for Business local não recebem minhas mensagens  <br/> |O envio de mensagens não será concluído quando os usuários do Microsoft Teams tentarem enviar uma mensagem para outro indivíduo que esteja usando o Skype for Business local. <br/> | Existe suporte para a interoperabilidade entre o Teams e os usuários hospedados no Skype for Business Online. Os usuários do Teams podem enviar mensagens individuais 1:1 para usuários fora do Teams que usem o Skype for Business Online. <br/> Não existe suporte para a interoperabilidade entre o Teams e os usuários hospedados no Skype for Business local. Os usuários do Teams não podem enviar mensagens individuais 1:1 para usuários fora do Teams que usem o Skype for Business local. <br/> |02/11/2016  <br/> |

## <a name="client"></a>Cliente
|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|As equipes não atualiza automaticamente   <br/> | Quando o Microsoft Teams é instalada para arquivos de programa usando scripts de instalação e não para o local padrão, o cliente não atualização automática quando novas versões estão disponíveis.    <br/> | Por design. Certifique-se instalar o aplicativo no local padrão: user\Appdata.  <br/> | 9/7/17  <br/> |

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Symlink ou mappying uma unidade de C:\users faz com que app à inicialização à tela branca  <br/> | Quando o Microsoft Teams é instalada para arquivos de programa usando scripts de instalação e não para o local padrão, o cliente não atualização automática quando novas versões estão disponíveis.   <br/> | Por design. Certifique-se instalar o aplicativo no local padrão: user\Appdata. Se o mapeamento deve existir, você deve usar a versão da web do Microsoft Teams.  <br/> | 9/7/17  <br/> |

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Symlink ou mapear uma unidade para c:\users causará app à inicialização à tela branca  <br/> |Quando o local padrão da C:\users\<usuário > \appData é alterada ao mover a pasta C:\users ou usando symlink, o aplicativo será iniciado com uma tela branca.   <br/> |Não há nenhum trabalho conhecido ao redor. Se o mapeamento deve existir, você deve usar a versão da web do Microsoft Teams.   <br/> |13/03/2017  <br/> |

## <a name="environment"></a>Ambiente
|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|As caixas de correio de grupos não estão habilitadas para fins de arquivamento (armazenamento extra)  <br/> |No Centro de Segurança e Conformidade do Office 365, os administradores globais não conseguem habilitar o arquivamento nas caixas de correio de grupos. Eles só conseguem em caixas de correio de usuários.  <br/> |Se a capacidade da caixa de correio do grupo estiver quase cheia, entre em contato com o Suporte do Microsoft Office para aumentar o tamanho da caixa de correio.  <br/> |01/02/2017  <br/> |

## <a name="guest-access"></a>Acesso de convidado
|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Os cliente da UE e da APAC recebem um erro quando adicionam um usuário convidado de outro locatário    <br/> | Para os clientes da UE e da APAC, ocorre um atraso na replicação entre o Microsoft Teams e o Azure Active Directory. Quando usuários de um locatário da UE ou da APAC tentam adicionar um usuário convidado de outro locatário, eles recebem uma mensagem de erro solicitando nova tentativa.   <br/> |Clique mais uma vez no botão Tentar Novamente para adicionar o usuário convidado.  <br/> |08/11/2017  <br/> |

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|O Wiki não é criado para canais criados por convidados  <br/> |Quando um convidado cria um novo canal, a guia **Wiki** não é criada. Não existe forma de anexar manualmente a guia **Wiki** ao canal. <br/> |Não há solução alternativa.  <br/> |20/09/2017  <br/>|

## <a name="meetings"></a>Reuniões
|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Os usuários não podem acessar reuniões/conectores, mas têm caixas de correio Exchange Online. <br/> |Cliente ativamente EWS impede que os serviços no Exchange Online, mas precisa ter MS Teams compatível com dentro políticas do EWS. <br/> |Para tornar o MS Teams compatível com, você deve adicionar a seguinte sequência de agente do usuário for MS Teams dentro do EWSAllowList: *skypespaces*, incluindo asteriscos. O comando completo é: set-organizationconfig - ewsallowlist *skypespaces*<br/> Para obter mais informações:https://technet.microsoft.com/en-us/library/aa997443(v=exchg.160).aspx <br/> |30/5/17  <br/>|

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Skype for Business obrigatório para algumas reuniões  <br/> |O seu calendário de reuniões é convenientemente exibido no Microsoft Teams. Para inserir uma reunião, clique em **Entrar**. <br/> Enquanto continuamos o desenvolvimento nesta área, se esta reunião foi agendada com o Skype for Business e você clicar em **Entrar**, o Microsoft Teams iniciará seu cliente Skype for Business para concluir sua entrada na reunião. As reuniões agendadas no Microsoft Teams iniciarão diretamente no produto.  <br/> No futuro, simplificaremos essa experiência.  <br/> |Clique em **Entrar**. O Microsoft Teams decide de forma inteligente se o Skype for Business é obrigatório para o usuário entrar na reunião com base na URL incluída na descrição da reunião.  <br/> |13/03/2017  <br/> |

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|**Reuniões**perdidas ser descoberto usando a descoberta automática Exchange. <br/> Microsoft Teams ainda não dá suporte a caixas de correio no Exchange hospedadas no ícone na barra de navegação esquerdo <br/> |O ícone de **reuniões** na barra de aplicativos é atualmente somente habilitada para usuários cujas caixas de correio está na multilocatário do Office 365 e um selecione poucos dedicada usuários cujo local da caixa de correio pode - locais e Exchange dedicado. Isso está sob investigação; no entanto, não há previsão para a entrega desse recurso.  <br/> |Não há solução alternativa.  <br/> |13/03/2017  <br/>|

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Número máximo de participantes de reuniões  <br/> |Cada reunião do Microsoft Teams pode ter até 80 participantes.  <br/> |Não há solução alternativa.  <br/> |13/03/2017  <br/> |

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|As reuniões não estão disponíveis  <br/> |A funcionalidade e o ícone da reunião não estão disponíveis quando a caixa de correio do Exchange está hospedada (ou estabelecida) localmente.  <br/> |Atualize para o Exchange 2016 CU3 ou posterior para implantações locais.  <br/> |28/02/2017  <br/> |

## <a name="mobile"></a>Mobile

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Não é possível ver os canais de auto-favorited  <br/> |Alguns membros não conseguem ver auto-favorited canais em que o aplicativo móvel.  <br/> |Membros devem entrar para o aplicativo de área de trabalho ou web primeiro para ver os canais de auto-favorited em seus aplicativos móveis.  <br/> |4/30/18  <br/>|

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Os usuários podem não conseguir alternar entre contas em dispositivos móveis gerenciados pelo Intune  <br/> |Os usuários podem não conseguir alternar entre contas em dispositivos móveis gerenciados pelo Intune.  <br/> |Não há solução alternativa.  <br/> |20/09/2017  <br/>|

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Não é possível usar diversão seletor ou Giphys ou adesivos em aplicativos móveis  <br/> |Você não pode usar gifs, emojis ou adesivos nos clientes móveis.  <br/> |Não há solução alternativa.  <br/> |13/03/2017  <br/> |

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Diferenças de Layout de equipes do cliente móvel  <br/> |As equipes estão listadas em ordem alfabética e os canais não podem ser recolhidos no cliente móvel.  <br/> |Não há solução alternativa.  <br/> |13/03/2017  <br/>|


## <a name="people"></a>Pessoas
|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Fotos de perfil de usuário  <br/> | Atualmente equipes não tem um mecanismo para impedir que usuários alterem as fotos. A equipe BTS atendeu com a equipe de desenvolvimento que tem o seguinte para consideração a arquivados: 108874 do recurso: política de TI para desabilitar o carregamento de fotos de perfil   <br/> | Se você tiver clientes que gostariam a capacidade de impedir o carregamento de fotos de perfil em equipes, tenha-los adicionar seu caso de negócios e votar para comentários aqui:https://microsoftteams.uservoice.com/forums/555103-public/suggestions/18600505-disable-user-ability-to-change-profile-photos
 <br/> |3/1/17 <br/> |

## <a name="provisioning"></a>Provisionamento
|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Usuário do SharePoint incorreto criado para o site do Microsoft Teams SharePoint  <br/> |O criador do SharePoint para um grupo do Microsoft Teams aparece como um administrador do SharePoint, e não o usuário correto.  <br/> Ao fazer uma auditoria no console de administração do SharePoint, o criador da página de coleta de sites associado ao Grupo do Office 365 criado na equipe no Microsoft Teams é o administrador do SharePoint.  <br/> |Não há solução alternativa.  <br/> |21/07/2017  <br/> |

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Os usuários não conseguem criar uma equipe  <br/> |A sua empresa pode ter definido uma política que restringe quem pode criar grupos ou equipes no Office 365.  <br/> |Verifique com o seu administrador de TI para entender a política da sua empresa para a criação de grupos e equipes.  <br/> |13/03/2017  <br/> |

## <a name="tabs"></a>Guias
|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Guia de site, levando a confusão do cliente  <br/> |Guias de site não são equivalentes ao seu navegador. Um número de sites, especialmente aquelas que exija autenticação ou usar pop-ups, não funcionará quando fixados como uma guia de site.  <br/> |Estamos trabalhando em melhorando a interface do usuário para tornar mais nítido para clientes.  <br/> |5/2/18  <br/> |

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Guias não funcionam desde a habilitação do acesso condicional <br/> |Algumas guias não podem carregar mais no cliente Desktop desde a habilitação do acesso condicional no locatário do. As guias de carga ao usar o cliente Web. Algumas guias que podem ser afetados são: PowerBI, formulários, VSTS, PowerApps e lista do SharePoint.  <br/> |Para ver as guias afetadas, você deve usar equipes em borda, IE ou Chrome com a extensão de contas do Windows 10 instalada. Algumas guias ainda dependem da autenticação de web, que não está funcionando no cliente da área de trabalho quando a autoridade de certificação está habilitada. Estamos trabalhando com parceiros para habilitar esses cenários; até agora, podemos habilitou planejador, OneNote e Stream. <br/> |4/5/18  <br/>|

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|A lista de espaços de trabalho não está em ordem alfabética  <br/> |Os clientes que alternarem espaços de trabalho ao adicionar uma guia do PowerBI encontrarão uma lista de espaços de trabalho fora da ordem alfabética entre os quais alternar.  <br/> |Não há solução alternativa.  <br/> |13/03/2017  <br/>|

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|A barra de rolagem desaparece ao selecionar relatórios  <br/> |Os usuários que adicionam relatórios do PowerBI não conseguem percorrer uma lista mais longa que uma tela de relatórios sem perder a barra de rolagem.  <br/> |Use as setas para cima e para baixo para percorrer a lista.  <br/> |13/03/2017  <br/>|

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|As equipes Planejador integração com Planejador online <br/> |Partições de memória de tarefas no planejador não aparecem na experiência online do planejador.  <br/> |Não há solução alternativa. <br/> |28/02/2017  <br/>|

## <a name="teams"></a>Microsoft Teams
|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|O carregamento de fotos para o Teams não está bloqueado no Outlook Web App/Outlook, embora isso seja um requisito da política   <br/> | O Teams permite que os usuários carreguem fotos diretamente para o Office 365, apesar de as configurações da política em vigor impedirem o carregamento de fotos para o Outlook Web App.   <br/> |<br/>  |16/10/2017  <br/> |

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|A lista de equipes públicas não exibe todas as equipes  <br/> |A lista de equipes públicas está baseada no Microsoft Graph.  <br/> |Se você não vê uma equipe, tente pesquisá-la na caixa de pesquisa superior à direita.  <br/> | 21/07/2017  <br/>|

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Nomes de equipe que contêm caracteres especiais podem criar erros para a criação de reunião  <br/> |Usuário receberá a mensagem de **erro** em vermelho ao tentar criar uma reunião para uma equipe com caracteres especiais no nome de usuário.   <br/> |Renomeie ou recriar equipe com um nome que não contém um "/".  <br/> |13/07/2017  <br/> |

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Um nome de equipe com um &amp; símbolo nela rompe a funcionalidade de conector  <br/> |Quando o nome de uma equipe é criado com o símbolo &amp;, os conectores dentro da equipe/grupo não podem ser estabelecidos.  <br/> |Não use caracteres especiais no nome de equipes.  <br/> |21/06/2017  <br/> |

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Máximo de 2500 membros de equipe  <br/> |Cada equipe do Microsoft Teams pode ter no máximo 2500 membros.  <br/> |Não há solução alternativa.  <br/> |13/03/2017  <br/> |

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|A exclusão de uma equipe também excluirá o grupo associado a ela  <br/> |Os usuários podem não perceber que o Grupo do Office 365 subjacente é excluído quando a equipe é excluída. Além disso, se o grupo do Office 365 subjacente for excluído, a equipe será excluída também.  <br/> |Idiomas adicionais no Microsoft Teams fornecem essa informação ao usuário. Essa informação não está presente na interface dos Grupos do Office 365. Seu help desk pode recuperar uma equipe/grupo excluído.  <br/> |13/03/2017  <br/> |

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|  
|Aplicativo de área de trabalho equipes mostrando tela branca  <br/> | <br/> |Tente excluir ou reinstalar os drivers de gráficos no computador, ou iniciar às equipes de uma linha de comando com um sinalizador GPU disable:<ul><li>Para Windows: Abra o prompt de comando e insira o seguinte: cd %localappdata%\microsoft\teams\current execute Teams.exe – disable-gpu</li><li>Para Mac: Iniciar Terminal e insira o seguinte: cd \Applications pasta Microsoft\ Teams.app/Contents/MacOS/Teams – disable-gpu</li></ul> <br/> |<br/> |

