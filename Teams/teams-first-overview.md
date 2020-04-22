---
title: Implantar o Microsoft Teams primeiro
author: LaszloSomi
ms.author: lsomi
manager: swerth
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: lsomi
localization_priority: Normal
search.appverid: MET150
description: Use esta orientação para implementar o Microsoft Teams como sua primeira carga de trabalho do Office 365.
ROBOTS: NOINDEX, NOFOLLOW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9db6b2192224e796475c903cf5eeeaa06ecdc8ee
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780370"
---
# <a name="roll-out-microsoft-teams-first"></a>Implantar o Microsoft Teams primeiro

O Microsoft Teams pode ajudar seus funcionários a ficar conectados e colaborar uns com os outros, especialmente no momento atual sem precedentes, em que o trabalho remoto é uma realidade dos funcionários do mundo todo. Poder conversar, fazer reuniões com vídeo e colaborar em documentos do Office dentro do teams pode ajudar as empresas a se manterem produtivas. Seja você uma pequena empresa, uma organização sem fins lucrativos ou de grande porte, você pode começar a usar o Microsoft Teams como a primeira carga de trabalho do pacote do Office 365 antes de implantar qualquer outro aplicativo ou serviço do Office.

Este artigo detalha as considerações que você deve fazer com a abordagem "Teams First".

> [!IMPORTANT]
> Embora as equipes possam ser a primeira carga de trabalho implantada na nuvem da sua organização, a implantação de equipes deve fazer parte da estratégia geral de implantação de nuvem.

Se você já tiver feito outros serviços do Office 365 e o Teams for a sua próxima carga de trabalho a ser distribuída (em vez do primeiro), comece com [como implantar o Microsoft Teams](How-to-roll-out-teams.md).

## <a name="start-here"></a>Comece aqui

Para começar a usar sua primeira implantação do Microsoft Teams, você precisará atender a pelo menos alguns pré-requisitos. A lista a seguir mostrará o que você deve ter em vigor para a sua organização para que as equipes possam ser habilitadas:

1.  Uma organização do Office 365 configurada com seu nome de domínio

2.  Conectividade do Azure Active Directory (AAD Connect) ou solução de sincronização de identidade de nuvem semelhante – com todos os atributos necessários sincronizados com seu locatário  
    Para entender os atributos sincronizados com a sincronização do AAD, leia a [sincronização do Azure ad Connect: atributos sincronizados com o Azure Active Directory](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)

3.  Licenças de usuário adequadas atribuídas para Teams  
    Para entender o licenciamento do Teams, leia [o licenciamento do Office 365 para Microsoft Teams](office-365-licensing.md)

4.  Rede da organização preparada para equipes  
    Para entender a preparação da rede, leia [preparar a rede da sua organização para equipes](prepare-network.md).

5.  Permitir o acesso à rede para o Exchange, SharePoint e OneDrive for Business no Office 365: [URLs e intervalos de endereços IP do office 365](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).

> [!NOTE]
> Os locatários criados após 1º de setembro de 2019 são provisionados no modo somente Teams.
> 
> [!IMPORTANT]
> Se você tiver o Skype for Business Server implantado e seu locatário tiver sido provisionado após 1º de setembro de 2019, entre em contato com o suporte Premier para habilitar os recursos de coexistência do teams. Verifique se a "política de atualização da organização" está definida como ' Island Mode ' <span class="underline">antes</span> de atribuir licenças de equipe a um usuário.

## <a name="migration-starting-points"></a>Pontos de partida de migração

Sua jornada ao Office 365 e recursos disponíveis no Microsoft Teams, dependendo do seu ponto de partida e da existência do Skype for Business ou do Lync Server local. As seções a seguir detalham os recursos básicos e as opções de configuração, além dos pré-requisitos anteriores. Dividimos os cenários de ponto de partida nos seguintes tópicos:

**Configuração de equipes de locatário**: os modos locatário e usuário são usados para controlar o comportamento do destinatário. Essas configurações podem ser atribuídas no nível do locatário ou no nível do usuário em uma organização. Para saber mais, leia [coexistência com o Skype for Business](coexistence-chat-calls-presence.md).

**Chat/comunicação externa no Teams**: os serviços de chat fazem referência a conversas de chat ponto a ponto ou em grupo dentro e organização ou externamente à organização. A comunicação externa também é conhecida como Federação no Skype for Business.

**Criar e exibir reuniões no Microsoft Teams**: um usuário sempre pode criar reuniões online por meio do suplemento do Outlook Teams e do dial-in PSTN está disponível em todos os cenários depois que o usuário é licenciado. Teams e informações de calendário do Skype for Business Store na caixa de correio do Exchange do usuário. No Exchange Server local, o Exchange Server 2016 CU3 ou superior para o cliente do teams deve ser capaz de interagir com a caixa de correio do usuário. Sem acesso à caixa de correio do Exchange o ícone de calendário no Teams não será exibido e ele não poderá exibir, criar ou modificar reuniões no cliente do teams.

**Recursos de chamada VoIP/PSTN no Teams**: as chamadas podem ser VoIP ou rede telefônica pública comutada (PSTN). A conectividade de VoIP acontece nativamente entre clientes do Teams, enquanto a conectividade PSTN ocorre quando um usuário disca para um número de telefone externo.  

O Microsoft Teams dá suporte a dois tipos de conectividade PSTN. Plano de chamadas da Microsoft, quando a Microsoft fornece uma infraestrutura de telefonia, incluindo o número de telefone de um usuário ou configuração de roteamento direto, em que o cliente fornece a conectividade de telefonia em um controlador de borda de sessão (SBC) para o usuário do teams.  
Para saber mais, leia [qual plano de chamadas é ideal para você?](calling-plan-landing-page.md) e [Roteamento direto do sistema telefônico](direct-routing-landing-page.md).

**Colaboração entre equipes e canais no Teams**: no Teams, o Teams é um grupo de pessoas reunidas para trabalho, projetos ou interesses comuns. As equipes são compostas de canais. Cada canal é criado em torno de um tópico, como "eventos da equipe", um nome de departamento ou apenas para diversão. Os canais são onde você mantém reuniões, têm conversas e trabalham em arquivos juntos. Durante a colaboração

**Onedrive for Business (compartilhamento de arquivos P2P) no Teams**: fora de equipes e canais, os usuários do teams podem compartilhar arquivos ponto a ponto usando o onedrive for Business ou outros programas de compartilhamento ponto a ponto, como arquivos Citrix, Dropbox, Box e Google Drive. Para o OneDrive for Business, um usuário deve ter uma licença do SharePoint Online atribuída.

**Plataforma do aplicativo**: os aplicativos fornecem ferramentas de ponta de tudo para a sua organização para tirar o máximo proveito do teams. Esses aplicativos combinam a funcionalidade de guias, extensões de mensagens, conectores e bots fornecidos pela Microsoft, criados por um terceiro ou por desenvolvedores em sua organização.

**Recursos de segurança e conformidade:** O Teams tem uma ampla gama de informações para ajudá-lo com áreas de conformidade, incluindo políticas de retenção, proteção contra perda de dados (DLP), descoberta eletrônica e retenção legal para canais, chats e arquivos, pesquisa de logs de auditoria. Para saber mais, leia sobre [segurança e conformidade no Microsoft Teams](security-compliance-overview.md).  

> [!NOTE]
> Os recursos avançados de descoberta eletrônica exigem licenciamento e5.

[Compare as opções de licenciamento](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).

Saiba [como o Exchange e o Microsoft Teams interagem](exchange-teams-interact.md) para saber quais recursos de conformidade estão disponíveis no seu cenário.

## <a name="organizations-span-classunderlinewithoutspan-skype-for-business-or-lync-server"></a>Organizações **<span class="underline">sem</span>** o Skype for Business ou o Lync Server

Este ponto de partida pressupõe que sua organização não use o Skype for Business ou o Lync Server atualmente, e o Teams será o seu primeiro aplicativo no Office 365. A tabela a seguir detalha a configuração de alto nível e os recursos do usuário final do teams para serviços essenciais.

<table>
<thead>
<tr class="header">
<th>Item</th>
<th>Observações</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Configuração de equipes de locatários</td>
<td>Modo somente equipes, todos os recursos de chat e chamadas estão apenas nas equipes</td>
</tr>
<tr class="even">
<td>Chat/comunicação externa no Microsoft Teams</td>
<td><p>Comunicação interna (organização intra Office 365) e comunicação de chat externa possível do teams</p>
<p><em>Observação: as entradas DNS devem ser configuradas para acesso externo. Os registros DNS do Skype for Business são necessários, mesmo que você não tenha o Skype for Business no local ou o Office 365 para permitir a Federação com ambientes do Lync e do Skype for Business.<br />
<a href="https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records">Registros de sistema de nome de domínio externo do Office 365</a></em></p></td>
</tr>
<tr class="odd">
<td><em>Criar e exibir reuniões no Microsoft Teams</em></td>
<td><p><em>Capaz de criar reuniões via suplemento do Outlook</em></p>
<p><em>O recurso de discagem PSTN e conexão discada está disponível com as licenças de audioconferência.<br />
Observação: o acesso ao calendário do teams requer o Exchange 2016 CU3 implantado no local com o Exchange Hybrid establishs: <a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">criar uma implantação híbrida com o assistente de configuração híbrida</a><br />
Além da configuração híbrida do Exchange, estabelecer a autenticação OAuth do Exchange: <a href="https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help">Configurar a autenticação OAuth entre organizações Exchange e Exchange Online</a></em></p></td>
</tr>
<tr class="even">
<td>Recursos de chamada<br />
VoIP/PSTN no Teams</td>
<td><p>VoIP interna e externamente para o locatário está disponível</p>
<p>Os serviços PSTN podem ser configurados pelo sistema telefônico da Microsoft, além de adicionar um plano de chamadas da Microsoft ou roteamento direto.</p></td>
</tr>
<tr class="odd">
<td>Colaboração entre equipes e canais no Teams</td>
<td><p>Para ter experiência total, incluindo recursos de conformidade, uma licença do SharePoint Online precisa ser atribuída ao usuário.</p>
<p>A migração de sites do SharePoint locais existentes não é necessária.</p></td>
</tr>
<tr class="even">
<td>OneDrive for Business (compartilhamento de arquivos P2P)</td>
<td>O OneDrive for Business exige que um usuário tenha uma licença do SharePoint Online atribuída. Sem essa licença, o compartilhamento de arquivos ponto a ponto não será possível.</td>
</tr>
<tr class="odd">
<td>Plataforma do aplicativo</td>
<td>Os usuários poderão usar os aplicativos designados para eles de acordo com as políticas da sua empresa.<br />
Saiba mais aqui: <a href="https://docs.microsoft.com/microsoftteams/admin-settings">configurações de administrador para aplicativos no Microsoft Teams</a></td>
</tr>
<tr class="even">
<td>Recursos de segurança e conformidade</td>
<td><ul>
<li><p>Políticas de retenção estão disponíveis</p></li>
<li><p>a descoberta eletrônica e a retenção legal para conformidade com mensagens de canal são aceitas</p></li>
<li><p>Políticas de prevenção contra perda de dados (DLP) estão disponíveis</p></li>
</ul>
<p>Conjunto de recursos completo disponível com o Exchange Online, o Exchange local oferece suporte para a maioria desses recursos, consulte</p>
<p><a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">Como o Exchange e o Teams interagem</a></p>
<p>para obter uma lista completa</p></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-without-skype-for-business-or-lync-server"></a>Etapas de capacitação para organizações sem o Skype for Business ou o Lync Server

1.  Conheça pré-requisitos detalhados descritos na seção iniciar aqui acima

2.  Alternar locatário para o modo somente do Teams (somente para locatários existentes): [Configurando suas configurações de coexistência e atualização](setting-your-coexistence-and-upgrade-settings.md).

3.  Configure seu locatário de acordo com as políticas de negócios/empresa da sua empresa: [gerenciar as configurações do Microsoft Teams para sua organização](enable-features-office-365.md).

4.  Implantar o cliente do teams para seus usuários: [obter clientes para Teams](get-clients.md)

5.  Orientar o programa de adoção  
    [Adotar o Microsoft Teams](adopt-microsoft-teams-landing-page.md)
    
    [Lista de verificação de início rápido da adoção do Microsoft Teams](teams-adoption-quick-start-checklist.md)

6.  Começar a mover outras cargas de trabalho para o Office 365

## <a name="organizations-span-classunderlinewithspan-skype-for-business-or-lync-server"></a>Organizações **<span class="underline">com</span>** o Skype for Business ou o Lync Server

Este ponto de partida pressupõe que sua organização utilize o Skype for Business 2019 ou 2015 + ou o Lync 2013 + Server no local. Já temos uma ampla orientação para as organizações que migram de servidores locais para o Microsoft Teams e devem ser seguidas nesses cenários. Esta orientação é específica do cenário que o Microsoft Teams é o primeiro aplicativo que você usa no Office 365. A tabela a seguir detalha a configuração de alto nível e os recursos do usuário final do teams para serviços essenciais.

<table>
<thead>
<tr class="header">
<th>Item</th>
<th>Observações</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Configuração de equipes de locatários</td>
<td>Modo de ilhas</td>
</tr>
<tr class="even">
<td>Chat/comunicação externa no Microsoft Teams</td>
<td>Interno somente dentro de seu próprio locatário, a comunicação externa (Federação) está via sua implantação do Skype for Business ou do Lync Server</td>
</tr>
<tr class="odd">
<td>Criar e exibir reuniões no Microsoft Teams</td>
<td><p>Capaz de criar reuniões via suplemento do Outlook</p>
<p>O recurso de discagem PSTN e conexão discada está disponível com as licenças de audioconferência.<br />
O acesso ao calendário de equipes requer o Exchange 2016 CU3 local instalado com o Exchange Hybrid estabelecido:<br />
<a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">Criar uma implantação híbrida com o assistente de configuração híbrida</a></p></td>
</tr>
<tr class="even">
<td>Recursos de chamada<br />
VoIP/PSTN no Teams</td>
<td><p>VoIP internamente para o locatário está disponível</p>
<p>Os serviços de PSTN ou de plano de chamada não estão disponíveis até que o usuário seja movido para a experiência apenas com o Microsoft Teams</p></td>
</tr>
<tr class="odd">
<td>Colaboração entre equipes e canais no Teams</td>
<td><p>Para ter experiência total, incluindo recursos de conformidade, uma licença do SharePoint Online precisa ser atribuída ao usuário.</p>
<p>A migração de sites do SharePoint locais existentes não é necessária.</p></td>
</tr>
<tr class="even">
<td>OneDrive for Business (compartilhamento de arquivos P2P)</td>
<td>O OneDrive for Business exige que um usuário tenha uma licença do SharePoint Online atribuída. Sem essa licença, o compartilhamento de arquivos por ponto não será possível.</td>
</tr>
<tr class="odd">
<td>Plataforma do aplicativo</td>
<td>Os usuários poderão usar os aplicativos designados para eles de acordo com as políticas da sua empresa.<br />
Saiba mais aqui: <a href="https://docs.microsoft.com/microsoftteams/admin-settings">configurações de administrador para aplicativos no Microsoft Teams</a></td>
</tr>
<tr class="even">
<td>Recursos de segurança e conformidade</td>
<td><ul>
<li><p>Políticas de retenção estão disponíveis</p></li>
<li><p>a descoberta eletrônica e a retenção legal para conformidade com mensagens de canal são aceitas</p></li>
<li><p>Políticas de prevenção contra perda de dados (DLP) estão disponíveis</p></li>
</ul>
<p>Conjunto de recursos completo disponível com o Exchange Online, o Exchange local oferece suporte para a maioria desses recursos, consulte</p>
<p><a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">Como o Exchange e o Teams interagem</a></p>
<ul>
<li><p>para obter uma lista completa</p></li>
</ul></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-with-skype-for-business-server"></a>Etapas de capacitação para organizações com o Skype for Business Server  

1.  Conheça pré-requisitos detalhados na seção início aqui.

2.  Alternar o locatário para o modo de ilhas (para locatários provisionados após 9/1/2019, entre em contato com o suporte Premier para fazer essa alteração)  
    [Definir suas configurações de coexistência e atualização](setting-your-coexistence-and-upgrade-settings.md)

3.  Configurar seu locatário de acordo com as políticas de negócios/empresa da empresa  
    [Gerenciar as configurações do Microsoft Teams para sua organização](enable-features-office-365.md)

4.  Implantar o cliente do teams  
    [Obter clientes para o Teams](get-clients.md)

5.   Orientar o programa de adoção  
    [Adotar o Microsoft Teams](adopt-microsoft-teams-landing-page.md)
    
    [Lista de verificação de início rápido da adoção do Microsoft Teams](teams-adoption-quick-start-checklist.md)

6.  Começar a mover outras cargas de trabalho para o Office 365

7.  Estabeleça o Skype for Business Hybrid e siga os caminhos de atualização recomendados para o Skype for Business e para os servidores Lync  
    [Atualize o Skype for Business no local para o Microsoft Teams](upgrade-to-teams-execute-skypeforbusinesshybridonprem.md)

## <a name="closing-statement"></a>Instrução de fechamento

O Microsoft Teams pode ser um habilitador para sua organização reunir todos os funcionários, operadores de informações e trabalhadores de primeira mão, juntos em uma única plataforma. Você pode [começar](https://products.office.com/microsoft-teams/group-chat-software) hoje mesmo. Você pode manter contato com todos os nossos comunicados mais recentes e atualizações de produtos mensais [aqui](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog).

Além disso, como as empresas de todo o mundo estão gerenciando a situação COVID-19 atual, criamos uma série de conteúdo que ajudará você a usar o Microsoft Teams para obter o máximo de impacto em sua organização.

  - Nosso [compromisso com os clientes durante a COVID-19](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)

  - [duas semanas em: o que aprendemos sobre o trabalho remoto](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/18/making-the-switch-to-remote-work-5-things-weve-learned/)

  - [Fornecendo reuniões e eventos online](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/delivering-online-meetings-events/)

  - [Ajudar empresas pequenas e de médio porte a trabalhar remotamente com o Teams](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/helping-smb-customers-work-remotely-microsoft-teams/)

  - [Transformação digital de eventos dinâmicos: Bob Bejan observações do Frontline](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/13/digital-transformation-live-events-bob-bejans-observations-frontline/)

  - [As 9 principais maneiras que o TI da Microsoft está possibilitando o trabalho remoto para seus funcionários](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/top-9-ways-microsoft-it-enabling-remote-work-employees/)

  - [Trabalhe remotamente, fique seguro — dicas para CISOs](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/work-remotely-stay-secure-ciso-tips/)

  - [Ajudando professores e alunos a fazer a mudança para o aprendizado remoto](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/11/helping-teachers-students-switch-remote-learning/)

  - [Manter-se produtivo enquanto trabalha remotamente com o Microsoft Teams](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/10/staying-productive-while-working-remotely-with-microsoft-teams/)

## <a name="support-services-reference"></a>Referência de serviços de suporte

O Microsoft Teams depende dos grupos do Exchange Online, do SharePoint Online, do OneDrive for Business e do Microsoft 365 para fornecer aos usuários uma experiência totalmente integrada do Office 365. Conforme observado acima, o Microsoft Teams funciona sem a implantação completa desses serviços – com recursos limitados. Você pode ler mais sobre o Teams e seus pré-requisitos aqui: [Bem-vindo ao Teams](teams-overview.md).

Para ver especificações sobre cada um dos serviços listados acima, siga os links abaixo:

  - O Exchange Online é usado para recursos de calendário e armazenamento de mensagens ponto a ponto no Teams. Para saber mais, leia [como o Exchange e as equipes interagem](exchange-teams-interact.md)

> [!IMPORTANT]
> Para a interoperabilidade do teams com o Exchange no local, você deve configurar o novo protocolo de autenticação OAuth do Exchange, conforme descrito em [Configurar a autenticação OAuth entre organizações Exchange e Exchange Online](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help).

  - O SharePoint é usado para compartilhamento de arquivos em canais, enquanto o/OneDrive for Business é usado para compartilhamento de arquivos no 1:1 ou em um chat em grupo. Para saber mais, leia [como o SharePoint Online e o onedrive for Business interagem com o Microsoft Teams](sharepoint-onedrive-interact.md).

  - Os [grupos do Microsoft 365](office-365-groups.md) são usados para criação/gerenciamento de equipes e canais.


## <a name="related-topics"></a>Tópicos relacionados

[Cartazes de soluções de telefonia e arquitetura de TI do Microsoft Teams](teams-architecture-solutions-posters.md#teams-as-part-of-microsoft-365)

[Planejar conectividade híbrida entre o Skype for Business Server e o Office 365](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity)

[Suporte a trabalhadores remotos usando o Teams](support-remote-work-with-teams.md)

[Trabalhe remotamente com o Office 365](https://aka.ms/remote-work)