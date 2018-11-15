---
title: Problemas conhecidos do Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 8/21/2018
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: marcl
search.appverid: MET150
description: Lista atual dos problemas conhecidos do aplicativo do cliente Microsoft Teams e experiência do administrador.
appliesto:
- Microsoft Teams
ms.openlocfilehash: ba794c49543740c2b436320d6639454ffb447659
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/15/2018
ms.locfileid: "26532274"
---
# <a name="known-issues-for-microsoft-teams"></a>Problemas conhecidos do Microsoft Teams

Este artigo lista os problemas conhecidos for Microsoft Teams, pela área de recurso.

## <a name="administration"></a>Administração

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Logs de auditoria podem informar um nome de usuário incorreta como iniciador quando alguém foi removido da equipe  <br/> |As equipes de equipe é um grupo moderno em AAD. Quando você adicionar ou remove um membro por meio da interface de usuário de equipes, o fluxo sabe exatamente o usuário que iniciou a alteração e o log de auditoria reflete as informações corretas. No entanto, se um usuário membro por meio de AAD de adiciona/remove, a alteração é sincronizada no back-end de equipes sem informando equipes que iniciou a ação. Microsoft Teams seleciona o primeiro proprietário da equipe como iniciador, eventualmente será refletido no log de auditoria.    <br/> |  <br/> |5/11/18  <br/> |

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Política EAF no Enhanced mitigação experiência Toolkit (EMET) incorretamente pode identificar as otimizações de área restrita hexavalente como ameaças. <br/> |Há um problema com seguro hexavalente nos quais a política de exportar endereço tabela acesso filtragem (EAF) no Enhanced mitigação experiência Toolkit (EMET) e no Windows Defender avançadas ameaça proteção (ATP) incorretamente pode identificar seguro hexavalente otimizações como ameaças. Isso faz com que as equipes não funcionarão corretamente.  <br/> | Para contornar esse problema, desative EAF para equipes. Você pode ler mais sobre o problema [diretrizes de atenuações EMET](https://support.microsoft.com/en-us/help/2909257/emet-mitigations-guidelines) para obter mais informações sobre o Windows Defender ATP e EAF política, consulte [Customize explorar proteção](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/customize-exploit-protection) <br/> |10/11/18 <br/> |

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Não é possível adicionar membros a equipes quando UsersPermissionToReadOtherUsersEnabled estiver definido como false  <br/> |Quando este valor é definido como false no AAD, cliente não é capaz de adicionar membros interno/externo em Teams da Microsoft e a seguinte mensagem de erro é exibida: "não podemos não pôde adicionar membro. Executamos em um problema. Tente novamente mais tarde." No entanto, os membros podem ser adicionados diretamente para grupos do Office 365.    <br/> |Altere essa configuração como true no AAD.  <br/> |4/10/18  <br/> |

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Gerenciamento de administração dos conectores de todo o locatário não está mais disponível  <br/> |Ao tentar adicionar um conector no cliente e versão online recebemos o erro: Ocorreu um erro inesperado. Tente novamente. Set-OrganizationConfig - ConnectorsEnabled = True   <br/> |Desabilite com configurações de equipes. Consulte o artigo de suportehttps://msdn.microsoft.com/microsoft-teams/connectors  <br/> |21/06/2017  <br/> |

## <a name="apps"></a>Aplicativos

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Opções de conector está ausente para algumas equipes  <br/> |Quando você clica com o botão direito em um canal, a opção Conectores não é exibida para nenhum membro da equipe.  <br/> |O criador da equipe precisa ter uma caixa de correio online; caso contrário, nenhuma opção do conector estará disponível. É esse o comportamento esperado.  <br/> |26/06/2017  <br/> |

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|"Atribuições" app permanece visble quando desabilitada  <br/> |Quando o aplicativo "Atribuições" está desabilitado no Centro de administração, permanece visível no cliente equipes para usuários licenciados EDU. Selecionando-o quando desabilitada retornará um erro indicando, "Doh! Algo deu errado..."  <br/> |Não há solução alternativa.  <br/> |12/29/17  <br/> |

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Não é possível excluir conectores como um proprietário de equipe  <br/> |A tentativa de excluir um conector como um proprietário, caso contrário, que pode adicionar um conector, enquanto "Permitir que os membros para criar, atualizar e remover conectores" está desabilitada gera um erro indicando o usuário não tem permissão para fazê-lo. <br/> |Habilitando temporariamente "Permitir que os membros criar, atualizar e remover conectores" permitirá que o proprietário para excluir o conector.  <br/> |27/7/18  <br/> |

## <a name="audio-conferencing"></a>Audioconferência

|**Problema**|**Comportamento/sintomas**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Os chamadores da PSTN com o mesmo "número From" são mostrados como o mesmo usuário na lista de participação de reunião.  <br/> |Quando vários chamadores por PSTN ingressem em uma reunião, e seus IDs do chamador são mascarados como um único número, eles serão exibidas como um chamador único na lista de participação da reunião.  <br/> |Não há solução alternativa.  <br/> |25/9/2017  <br/> |
|Painel de informações da reunião não está aparecendo forma intermitente.  <br/> |Painel de informações da reunião pode não aparecer no cliente de equipes, quando os usuários tentam procurar para números de telefone de ponte de conferência ou ID de conferência.  <br/> |Examinar detalhes da reunião ou calendário do Outlook para exibir números de telefone de ponte de conferência ou ID de conferência.  <br/> |25/9/2017  <br/> |
|Convites de reunião de suplemento do Outlook mostram caracteres corrompidos em coordenadas PSTN para localidades fora dos EUA.  <br/> |Ao agendar reuniões privadas usando o suplemento do Outlook for Microsoft Teams em um computador com localidades fora dos EUA, coordenadas PSTN podem conter caracteres corrompidos.  <br/> |Não há solução alternativa.  <br/> |25/9/2017  <br/> |
|Discagem externa precisa usar 5 dígitos ou mais.  <br/> |Os usuários que tentarem discar a partir de uma reunião precisam digitar em 5 ou mais dígitos, mesmo que a regra de normalização do plano de discagem está disponível para normalizar discagem curto dígitos em e. 164.  <br/> |Discar digitando o número total de DID ou o formato de número local em vez do número de ramal interno.  <br/> |25/9/2017  <br/> |
|Discagem externa de controle não está aparecendo forma intermitente.  <br/> |Discagem externa controle pode não estar visível do painel de informações da reunião.  <br/> |Não há solução alternativa.  <br/> |25/9/2017  <br/> |
|ID de conferência estático não tem suportado para reuniões de Teams da Microsoft.  <br/> |Se o administrador substitui a configuração de padrão de ID de conferência dinâmico a ID de conferência estático, essa configuração não terá efeito para reuniões de Teams da Microsoft. Consulte as [IDs de conferência de áudio usando dinâmicos em sua organização](/skypeforbusiness/audio-conferencing-in-office-365/using-audio-conferencing-dynamic-ids-in-your-organization.md).  <br/> |Não há solução alternativa.  <br/> |25/9/2017  <br/> |
|As coordenadas de reunião de PSTN não estão disponíveis para Skype para usuários do local de negócios  <br/> |Se o usuário for um Skype para usuário local de negócios, atribuído com Skype para Business Online, conferência de áudio e licenças de equipes, todas as reuniões agendadas usando equipes não incluirá as coordenadas de reunião de PSTN. <br/> |Não há solução alternativa.  <br/> |2/1/2018  <br/> |

## <a name="authentication"></a>Autenticação

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Ao tentar ingressar no Teams usando o Internet Explorer ou o Edge, o programa entra em loop e falha consistentemente e não entra.   <br/> | Sua organização usa Sites Confiáveis no Internet Explorer e o aplicativo baseado na Web do Teams não se conecta porque sites confiáveis não são permitidos para o Teams. <br/>|Para configurações do IE ou do painel de controle, com direitos de administrador ou de um objeto de diretiva de grupo, faça as seguintes alterações:<br/><ol><li>Em **Opções da Internet** &gt; **privacidade** &gt; **Avançado**, aceitar os cookies primários e de terceiros e a caixa de seleção para **sempre permitir cookies de sessão**.</li><li>Clique em **Opções da Internet** &gt; **segurança** &gt; **Sites confiáveis** &gt; **Sites**e adicione todos os seguintes:<ul><li>https://login.microsoftonline.com</li><li>https://\*.teams.microsoft.com</li></ul></li></ol><br/><b>OBSERVAÇÃO</b>: Sempre valide e permita todas as URLs confiáveis para o Teams e os requisitos do seguinte documento: [URLs e intervalos de endereços IP do Office 365](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).   <br/> |01/11/2017  <br/> |

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Limitações no complemento do Outlook  <br/> |Para usar o complemento do Outlook, você precisa fazer login no Teams usando a autenticação multifator (MFA). Se a MFA falhar no meio do processo de login, você ainda poderá fazer login no Teams, mas você receberá uma mensagem de erro quando tentar usar o complemento.  <br/> Até o momento, o complemento só está disponível para usuários do Windows.  <br/> O complemento não funcionará se você estiver usando uma autenticação de proxy.  <br/> | Não há solução alternativa. <br/> |02/08/2017  <br/> |

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Microsoft Teams será sempre acesse a conta de domínio PC.   <br/> |Se um usuário possui duas contas de equipes diferentes e tiver uma máquina com domínio habilitado, equipes usará o perfil de domínio na máquina para fazer logon automaticamente o usuário em equipes. Para alternar para a outra conta de equipes, o usuário deve manualmente saia do aplicativo e insira as credenciais para a segunda conta para fazer logon. Se o usuário fizer logoff do equipes e reinicia a máquina, durante a reinicialização, equipes automaticamente efetuará login usando o perfil do domínio. <br/> | Não há solução alternativa. <br/> |02/08/2017  <br/> |

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Falha de autenticação moderno - autenticação de formulários não habilitado  <br/> |Quando há uma falha inicial com a autenticação multifator, use o aplicativo web para a autenticação.  <br/> Para obter mais informações, consulte [Suporte ao parâmetro prompt=login dos Serviços de Federação do Active Directory (AD FS)](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-prompt-login).  <br/> |Marque essa configuração: `Set -MsolDomainFederationSettings -DomainName yourdomainhere -PreferredAuthenticationProtocol WsFed -SupportsMfa $False -PromptLoginBehavior Disabled`.  <br/> |19/06/2017  <br/> |

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Planejador de compilação de logon único (SSO) <br/> |O SSO não se aplica ao Planner. Será necessário iniciar sessão novamente sempre que você usar o Planner em cada cliente pela primeira vez.  <br/> |Não há solução alternativa. Estamos trabalhando em mais aprimoramentos de autenticação.  <br/> |28/02/2017  <br/> |

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Não é possível salvar a imagem de perfil  <br/> |Os usuários não podem salvar sua imagem de perfil quando a caixa de correio do Exchange é (hospedado hospedados) no local no Exchange 2016 CU2 ou inferior.  <br/> |Não há solução alternativa.  <br/> |28/02/2017  <br/> |

## <a name="browser"></a>Navegador

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Artefatos verdes do processamento de vídeos no Chrome  <br/> |Artefatos verdes aparecem enquanto exibindo vídeo ou compartilhamento de tela em uma chamada ou meetup no Chrome.  <br/> |Desabilite a configuração de aceleração de hardware no Chrome.  <br/> |03/08/2017  <br/> |

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Suporte para o cliente web do Safari  <br/> |Os usuários que tentam abrir o cliente Microsoft Teams no Safari são direcionados para baixar o cliente desktop. A Microsoft está examinando o suporte do Safari e compartilhará as atualizações por meio do [Roteiro do Microsoft Teams](https://aka.ms/TeamsRoadmap).  <br/> |Navegadores de internet, que incluem suporte para uso: Internet Explorer 11 +, Microsoft Edge 12 +, Chrome 51.0 + e Firefox 47.0 +.  <br/> |02/11/2016  <br/> |

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

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Visualização de URL não poderá mostrar para URL de todos os  <br/> |Alguns URL não poderá mostrar uma visualização.  Isso depende da URL original com a possibilidade de mostrar uma visualização. <br/> |Não há solução alternativa. <br/> |9/1/18 <br/> |

## <a name="chat"></a>Chat

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|@ Menções para mensagem excluída enviar notificação com link de canal  <br/> |Existe uma limitação conhecida notificação quando você estiver em mencionados em uma mensagem que será excluída; a notificação no feed navegarão para o canal, mas não para uma mensagem específica. <br/> | Por design <br/> | 3/28/17  <br/>|


## <a name="client"></a>Cliente

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|As equipes não atualiza automaticamente   <br/> | Quando o Microsoft Teams é instalada para arquivos de programa usando scripts de instalação e não para o local padrão, o cliente não atualização automática quando novas versões estão disponíveis.    <br/> | Por design. Certifique-se instalar o aplicativo no local padrão: `user\Appdata`.  <br/> | 9/7/17  <br/> |

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Symlink ou mappying uma unidade de C:\users faz com que app à inicialização à tela branca  <br/> | Quando o Microsoft Teams é instalada para arquivos de programa usando scripts de instalação e não para o local padrão, o cliente não atualização automática quando novas versões estão disponíveis.   <br/> | Por design. Certifique-se instalar o aplicativo no local padrão: `user\Appdata`. Se o mapeamento deve existir, você deve usar a versão da web do Microsoft Teams.  <br/> | 9/7/17  <br/> |

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Symlink ou mapear uma unidade para c:\users causará app à inicialização à tela branca  <br/> |Quando o local padrão do `C:\users\<user>\appData` mudou movendo o `C:\users` pasta ou usando symlink, o aplicativo será iniciado com uma tela branca.   <br/> |Não há nenhum trabalho conhecido ao redor. Se o mapeamento deve existir, você deve usar a versão da web do Microsoft Teams.   <br/> |13/03/2017  <br/> |

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
|Os usuários não podem acessar reuniões/conectores, mas têm caixas de correio Exchange Online. <br/> |Cliente ativamente EWS impede que os serviços no Exchange Online, mas precisa ter MS Teams compatível com dentro políticas do EWS. <br/> |Para tornar o MS Teams compatível com, você deve adicionar a seguinte sequência de agente do usuário for MS Teams dentro do EWSAllowList: `*skypespaces*`, incluindo asteriscos. O comando completo é:`set-organizationconfig -ewsallowlist *skypespaces*`<br/> Para obter mais informações:https://docs.microsoft.com/powershell/module/exchange/organization/Set-OrganizationConfig?view=exchange-ps <br/> |30/5/17  <br/>|

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Skype for Business obrigatório para algumas reuniões  <br/> |O seu calendário de reuniões é convenientemente exibido no Microsoft Teams. Para inserir uma reunião, clique em **Entrar**. <br/> Enquanto continuamos o desenvolvimento nesta área, se esta reunião foi agendada com o Skype for Business e você clicar em **Entrar**, o Microsoft Teams iniciará seu cliente Skype for Business para concluir sua entrada na reunião. As reuniões agendadas no Microsoft Teams iniciarão diretamente no produto.  <br/> No futuro, simplificaremos essa experiência.  <br/> |Clique em **Entrar**. O Microsoft Teams decide de forma inteligente se o Skype for Business é obrigatório para o usuário entrar na reunião com base na URL incluída na descrição da reunião.  <br/> |13/03/2017  <br/> |


|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Número máximo de participantes de reuniões  <br/> |Cada reunião do Microsoft Teams pode ter até 80 participantes.  <br/> |Não há solução alternativa.  <br/> |13/03/2017  <br/> |

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|As reuniões não estão disponíveis  <br/> |Funcionalidade de reunião não está disponível quando a caixa de correio do Exchange é (hospedado hospedados) no local na versão menor Exchange 2016 CU3.  <br/> |Atualize para o Exchange 2016 CU3 ou posterior para implantações locais.  <br/> |28/02/2017  <br/> |

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Sem áudio ao compartilhar conteúdo durante uma reunião de transmissão  <br/> |Quando o compartilhamento de conteúdo durante uma reunião de transmissão, o conteúdo compartilhado (link do youtube ou um arquivo de vídeo salvo) de áudio não pode ser ouve pelos participantes.  <br/> |Nenhum como isso é por design.  As equipes atualmente não oferece suporte a áudio de compartilhamento de conteúdo  <br/> |10/9/18  <br/> |

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

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Guia de página do SharePoint renderiza tela em branco<br/> |Domínios de vanity SharePoint Online não são suportados no momento. A experiência do usuário é uma tela em branco, quando o guia de página attemting para adicionar uma lista do SharePoint. <br/> |Não há solução alternativa. <br/> |8/20/18  <br/>|

## <a name="teams"></a>Microsoft Teams

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Logs de auditoria podem informar um nome de usuário incorreta como iniciador quando alguém foi removido da equipe  <br/> |As equipes de equipe é um grupo moderno em AAD. Quando você adicionar ou remove um membro por meio da interface de usuário de equipes, o fluxo sabe exatamente o usuário que iniciou a alteração e o log de auditoria reflete as informações corretas. No entanto, se um usuário membro por meio de AAD de adiciona/remove, a alteração é sincronizada no back-end de equipes sem informando equipes que iniciou a ação. Microsoft Teams seleciona o primeiro proprietário da equipe como iniciador, eventualmente será refletido no log de auditoria.    <br/> |  <br/> |5/11/18  <br/> |

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|O carregamento de fotos para o Teams não está bloqueado no Outlook Web App/Outlook, embora isso seja um requisito da política   <br/> | O Teams permite que os usuários carreguem fotos diretamente para o Office 365, apesar de as configurações da política em vigor impedirem o carregamento de fotos para o Outlook Web App.   <br/> |<br/>  |16/10/2017  <br/> |

|**Título do problema**|**Comportamento / Sintoma**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|A lista de equipes públicas não exibe todas as equipes  <br/> |A lista de equipes públicas está baseada no Microsoft Graph.  <br/> |Se você não vê uma equipe, tente pesquisá-la na caixa de pesquisa superior à direita. Além disso, os proprietários de equipe devem comunicar nomes de equipe para colegas de trabalho, desde que muitas equipes poderiam mostrada nos resultados da pesquisa. <br/> | 21/07/2017  <br/>|

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
|Aplicativo de área de trabalho equipes mostrando tela branca  <br/> | <br/> |Tente excluir ou reinstalar os drivers de gráficos no computador, ou iniciar às equipes de uma linha de comando com um sinalizador GPU disable:<ul><li>Para Windows: Abra o prompt de comando e digite o seguinte:`cd %localappdata%\microsoft\teams\current run Teams.exe --disable-gpu`</li><li>Para Mac: Iniciar Terminal e insira o seguinte:`cd \Applications folder Microsoft\ Teams.app/Contents/MacOS/Teams --disable-gpu`</li></ul> <br/> |<br/> |

