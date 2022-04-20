---
title: Distribuir Microsoft Teams Primeiro
author: LaszloSomi
ms.author: lsomi
manager: swerth
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: lsomi
ms.localizationpriority: medium
search.appverid: MET150
description: Use essas diretrizes para distribuir Microsoft Teams como sua primeira Microsoft 365 ou Office 365 carga de trabalho.
ROBOTS: NOINDEX, NOFOLLOW
appliesto:
- Microsoft Teams
ms.openlocfilehash: f6dba57003aaa58b9d0b72e7e866da261bed578e
ms.sourcegitcommit: 1d990582e2deb5f55ba9adada3e17377f792a141
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/19/2022
ms.locfileid: "64922682"
---
# <a name="roll-out-microsoft-teams-first"></a>Distribuir Microsoft Teams Primeiro

Microsoft Teams pode ajudar seus funcionários a se manterem conectados e colaborarem entre si, especialmente no momento sem precedentes atual em que o trabalho remoto é uma realidade de funcionários em todo o mundo. Poder conversar, fazer reuniões em vídeo e colaborar em documentos Office no Teams pode ajudar as empresas a se manterem produtivas. Seja uma pequena empresa, uma organização sem fins lucrativos ou de grande porte, você pode começar a usar o Teams como a primeira carga de trabalho dentro do Microsoft 365 ou do Office 365 antes de implantar qualquer outro Aplicativo do Office ou serviço.

Este artigo detalha as considerações que você deve fazer com a abordagem "Teams Primeiro".

> [!IMPORTANT]
> Embora Teams possa ser a primeira carga de trabalho implantada na nuvem da sua organização, a implantação Teams deve fazer parte de sua estratégia geral de implantação de nuvem.

Se você já tiver distribuído outros serviços Microsoft 365 ou Office 365 e o Teams for sua próxima carga de trabalho a ser implantada (em vez da primeira), comece com Como distribuir [Teams.](./deploy-overview.md)

## <a name="start-here"></a>Iniciar aqui

Para começar a usar a Teams First, você precisará atender, no mínimo, a alguns pré-requisitos. A lista a seguir mostrará o que você deve ter em vigor para sua organização antes que Teams possa ser habilitado:

1.  Uma Microsoft 365 ou Office 365 configurada com seu nome de domínio

2.  Azure Active Directory conectividade (AAD connect) ou uma solução de sincronização de identidade de nuvem semelhante – com todos os atributos necessários sincronizados com seu locatário  
    Para entender os atributos sincronizados com AAD, leia a sincronização de Conexão do [Azure AD:](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized) atributos sincronizados com Azure Active Directory

3.  Licenças de usuário apropriadas atribuídas para Teams  
    Para entender Teams licenciamento, leia Microsoft Teams [descrição do serviço](/office365/servicedescriptions/teams-service-description).

4.  Rede da organização preparada para Teams  
    Para entender a preparação da rede, [leia Preparar a rede da sua organização para Teams](prepare-network.md).

5.  Permitir o acesso à rede Exchange, SharePoint e OneDrive for Business no Microsoft 365 ou Office 365: [urLs Office 365 e intervalos de endereços IP](/office365/enterprise/urls-and-ip-address-ranges).

> [!NOTE]
> Os locatários criados após 1º de setembro de 2019 são provisionados Teams modo Somente.
> 
> [!IMPORTANT]
> Se você tiver Skype for Business Server e seu locatário tiver sido provisionado APÓS 1º de setembro de 2019, entre em contato com o suporte para habilitar os recursos de coexistência para Teams. Verifique se a "política de atualização em toda a organização" está definida como "Modo <span class="underline">ilha" antes</span> de atribuir Teams licenças a um usuário.

## <a name="migration-starting-points"></a>Pontos de partida da migração

Sua jornada para Microsoft 365 ou Office 365 recursos disponíveis no Teams dependendo do ponto de partida e da existência de Skype for Business ou servidor Lync local. As seções a seguir detalham as funcionalidades básicas e as opções de configuração, além dos pré-requisitos acima. Descrevemos os cenários de ponto de partida para os seguintes tópicos:

**Configuração Teams locatário**: os modos de locatário e de usuário são usados para controlar o comportamento do destinatário. Essas configurações podem ser atribuídas no nível do locatário ou no nível do usuário em uma organização. Para saber mais, leia [Coexistência com Skype for Business](coexistence-chat-calls-presence.md).

**Chat/Comunicação externa no Teams**: os serviços de chat referem-se a conversas de chat ponto a ponto ou em grupo dentro e na organização ou externamente à organização. A comunicação externa também é conhecida como federação no Skype for Business.

Criar e exibir reuniões no **Teams**: um usuário sempre pode criar reuniões online por meio do suplemento Outlook Teams e o discagem PSTN está disponível em todos os cenários depois que o usuário é licenciado. Teams e Skype for Business armazenar informações de calendário na caixa de correio Exchange usuário. O servidor Exchange local deve ser Exchange Server 2016 CU3 ou superior para que o cliente Teams possa interagir com a caixa de correio do usuário. Sem Exchange caixa de correio, o ícone calendário no Teams não será exibido e o usuário não poderá exibir, criar ou modificar reuniões no Teams cliente.

**Recursos de chamada VoIP/PSTN no Teams**: a chamada pode ser VoIP (Voice over IP) ou PSTN (Rede Telefônica Pública Comunada). A conectividade VoIP ocorre nativamente entre Teams clientes, enquanto a conectividade PSTN ocorre quando um usuário disca um número de telefone externo.  

Teams suporte a dois tipos de conectividade PSTN. Plano de Chamadas da Microsoft, quando a Microsoft fornece infraestrutura de telefonia, incluindo o número de telefone para um usuário ou configuração de Roteamento Direto, em que o cliente fornece a conectividade de telefonia em um controlador de borda de sessão (SBC) para o Teams usuário.  
Para saber mais, leia [Qual Plano de Chamadas é ideal para você?](calling-plan-landing-page.md) e [Sistema de Telefonia Roteamento Direto](direct-routing-landing-page.md).

**Teams e canais** de colaboração no Teams: em Teams, as equipes são grupos de pessoas reunidas para trabalho, projetos ou interesses comuns. Teams são compostas por canais. Cada canal é criado em torno de um tópico, como "Eventos de Equipe", um nome de departamento ou apenas por diversão. Os canais são onde você faz reuniões, conversa e trabalha em arquivos juntos. Durante a colaboração

**OneDrive for Business (compartilhamento de arquivos P2P) no Teams**: fora do Teams e canais, os usuários do Teams podem compartilhar arquivos ponto a ponto usando o OneDrive para empresas ou outros programas de arquivos de compartilhamento P2P, como Arquivos Citrix, DropBox, Box e Google Drive. Por OneDrive para empresas, um usuário deve ter uma licença SharePoint Online atribuída.

**Plataforma de** Aplicativos: os aplicativos fornecem ferramentas disponíveis para sua organização para obter mais Teams. Esses aplicativos combinam a funcionalidade de guias, extensões de mensagens, conectores e bots fornecidos pela Microsoft, criados por terceiros ou por desenvolvedores em sua organização.

Recursos de segurança e conformidade **:** o Teams tem uma ampla variedade de informações para ajudá-lo com áreas de conformidade, incluindo políticas de retenção, DLP (prevenção contra perda de dados), Descoberta Eletrônica e retenção legal para canais, chats e arquivos, pesquisa de log de auditoria. Para saber mais, leia [Segurança e conformidade Microsoft Teams](security-compliance-overview.md).  

> [!NOTE]
> Recursos avançados de Descoberta Eletrônica exigem o licenciamento do E5.

[Compare as opções de licenciamento](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).

Leia [como Exchange e Microsoft Teams interagir](exchange-teams-interact.md) para saber quais recursos de conformidade estão disponíveis em seu cenário.

## <a name="organizations-span-classunderlinewithoutspan-skype-for-business-or-lync-server"></a>**<span class="underline">Organizações sem</span>** Skype for Business ou Lync Server

Esse ponto de partida pressupõe que sua organização não utiliza o Skype for Business ou o Lync Server no momento e Teams será seu primeiro aplicativo no Microsoft 365 ou Office 365. A tabela a seguir detalha a configuração de alto nível e as funcionalidades do usuário final Teams para serviços principais.

<table>
<thead>
<tr class="header">
<th>Item</th>
<th>Observações</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Configuração Teams locatário</td>
<td>Teams modo somente, todos os recursos de chat e chamada estão Teams somente.</td>
</tr>
<tr class="even">
<td>Chat/Comunicação Externa no Teams</td>
<td><p>Comunicação interna (dentro Microsoft 365 ou Office 365) e comunicação de chat externo possível do Teams.</p>
<p><em>Observação: as entradas DNS devem ser configuradas para acesso externo. Skype for Business registros DNS são necessários mesmo que você não tenha um Skype for Business local ou no Microsoft 365 ou Office 365, para permitir a federação com ambientes Lync e Skype for Business:<br />
<a href="/office365/enterprise/external-domain-name-system-records">Registros do Sistema de Nomes de Domínio Externo</a></em></p></td>
</tr>
<tr class="odd">
<td>Criar e exibir Reuniões no Teams</td>
<td><p>Capaz de criar reuniões internas e externas Outlook suplemento.</p>
<p>A funcionalidade discar e discar PSTN está disponível com as licenças de Audioconferência.</p>
<p>Teams acesso ao calendário requer Exchange 2016 CU3+ local implantado com o Exchange híbrido estabelecido: crie uma implantação híbrida com o assistente de Configuração <a href="/exchange/hybrid-deployment/deploy-hybrid">Híbrida.</a> </p>

Além da configuração Exchange híbrida, estabeleça uma autenticação OAuth Exchange: configurar a autenticação [OAuth entre Exchange e Exchange Online organizações](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help). 

</p></td>
</tr>
<tr class="even">
<td>Recursos de chamada<br />
VoIP/PSTN no Teams</td>
<td><p>O VoIP interna e externamente para o locatário está disponível.</p>
<p>Os serviços PSTN podem ser configurados por meio do Telefone Microsoft, além de adicionar um Plano de Chamada da Microsoft ou Roteamento Direto.</p></td>
</tr>
<tr class="odd">
<td>Teams e canais de colaboração no Teams</td>
<td><p>Para obter experiência completa, incluindo recursos de conformidade, SharePoint uma licença do SharePoint Online precisa ser atribuída ao usuário.</p>
<p>A migração de sites SharePoint locais existentes não é necessária.</p></td>
</tr>
<tr class="even">
<td>OneDrive for Business (compartilhamento de arquivos P2P)</td>
<td>OneDrive for Business requer que um usuário tenha uma licença SharePoint Online atribuída. Sem essa licença, o compartilhamento de arquivos ponto a ponto não será possível.</td>
</tr>
<tr class="odd">
<td>Plataforma de aplicativo</td>
<td>Os usuários poderão usar os aplicativos designados disponíveis para eles de acordo com as políticas da sua empresa.<br />
Saiba mais aqui: <a href="/microsoftteams/admin-settings">Configurações de administrador para aplicativos no Teams</a></td>
</tr>
<tr class="even">
<td>Recursos de segurança e conformidade</td>
<td><ul>
<li><p>As políticas de retenção estão disponíveis.</p></li>
<li><p>Há suporte para Descoberta Eletrônica e Retenção Legal para conformidade em mensagens de canal.</p></li>
<li><p>As políticas de prevenção contra perda de dados (DLP) estão disponíveis.</p></li>
</ul>
<p>Conjunto de recursos completo disponível com Exchange Online; Exchange local dá suporte à maioria desses recursos. Para obter uma lista completa, <a href="/MicrosoftTeams/exchange-teams-interact">consulte Como Exchange e Teams interagir</a>.</p></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-without-skype-for-business-or-lync-server"></a>Etapas de habilitação para organizações sem Skype for Business ou Lync Server

1.  Atender aos pré-requisitos detalhados na seção Iniciar aqui acima

2.  Alterne o locatário Teams modo somente para locatários existentes: definindo [suas configurações de coexistência e atualização](setting-your-coexistence-and-upgrade-settings.md).

3.  Configure seu locatário de acordo com as políticas de negócios/empresa da sua empresa: gerencie Microsoft Teams [configurações para sua organização](enable-features-office-365.md).

4.  Implantar o Teams cliente para seus usuários: [obter clientes para Teams](get-clients.md)

5.  Impulsionar seu programa de adoção  
    [Adotar o Microsoft Teams](adopt-microsoft-teams-landing-page.md)
    
    [Lista de verificação de início rápido da adoção do Microsoft Teams](teams-adoption-quick-start-checklist.md)

6.  Comece a planejar a movimentação de outras cargas de trabalho para Microsoft 365 ou Office 365

## <a name="organizations-span-classunderlinewithspan-skype-for-business-or-lync-server"></a>**<span class="underline">Organizações com</span>** Skype for Business ou servidor Lync

Esse ponto de partida pressupõe que sua organização utiliza Skype for Business 2019 ou 2015+ ou Lync 2013+ servidor local. Já temos orientações abrangentes para organizações que migram de servidores locais para Teams e ela deve ser seguida para esses cenários. Essas diretrizes são específicas para o cenário Teams é o primeiro aplicativo que você utiliza no Microsoft 365 ou Office 365. A tabela a seguir detalha a configuração de alto nível e as funcionalidades do usuário final Teams para serviços principais.

<table>
<thead>
<tr class="header">
<th>Item</th>
<th>Observações</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Configuração Teams locatário</td>
<td>Modo ilhas.</td>
</tr>
<tr class="even">
<td>Chat/Comunicação Externa no Teams</td>
<td>Interna somente em seu próprio locatário, a comunicação externa (federação) é por meio da implantação do Skype for Business ou do servidor Lync.</td>
</tr>
<tr class="odd">
<td>Criar e exibir Reuniões no Teams</td>
<td><p>Capaz de criar reuniões internas e externas Outlook suplemento.</p>
<p>A funcionalidade discar e discar PSTN está disponível com as licenças de Audioconferência.</p>
<p>Teams de calendário requer Exchange 2016 CU3+ local implantado com Exchange híbrido estabelecido:<br />
<a href="/exchange/hybrid-deployment/deploy-hybrid">Crie uma implantação híbrida com o assistente de Configuração Híbrida.</a></p>
<p>O administrador pode controlar o suplemento Skype for Business Outlook por meio do atributo PreferredMeetingProviderForIslandsMode da política de reunião do Teams:<a href="/powershell/module/skype/set-csteamsmeetingpolicy"> set-csteamsmeetingpolicy</a>.</p> 
</td>
</tr>
<tr class="even">
<td>Recursos de chamada<br />
VoIP/PSTN no Teams</td>
<td><p>O VoIP internamente para o locatário está disponível.</p>
<p>Os serviços PSTN ou Plano de Chamada não estarão disponíveis até que o usuário seja movido para Teams somente experiência.</p></td>
</tr>
<tr class="odd">
<td>Teams e canais de colaboração no Teams</td>
<td><p>Para obter experiência completa, incluindo recursos de conformidade, SharePoint uma licença do SharePoint Online precisa ser atribuída ao usuário.</p>
<p>A migração de sites SharePoint locais existentes não é necessária.</p></td>
</tr>
<tr class="even">
<td>OneDrive for Business (compartilhamento de arquivos P2P)</td>
<td>OneDrive for Business requer que um usuário tenha uma licença SharePoint Online atribuída. Sem essa licença, o compartilhamento de arquivos por ponto não será possível.</td>
</tr>
<tr class="odd">
<td>Plataforma de aplicativo</td>
<td>Os usuários poderão usar os aplicativos designados disponíveis para eles de acordo com as políticas da sua empresa.<br />
Saiba mais aqui: <a href="/microsoftteams/admin-settings">Configurações de administrador para aplicativos no Teams</a></td>
</tr>
<tr class="even">
<td>Recursos de segurança e conformidade</td>
<td><ul>
<li><p>As políticas de retenção estão disponíveis.</p></li>
<li><p>Há suporte para Descoberta Eletrônica e Retenção Legal para conformidade em mensagens de canal.</p></li>
<li><p>As políticas de Prevenção contra Perda de Dados (DLP) estão disponíveis.</p></li>
</ul>
<p>Conjunto de recursos completo disponível com Exchange Online; Exchange local dá suporte à maioria desses recursos. Para obter uma lista completa, <a href="/MicrosoftTeams/exchange-teams-interact">consulte Como Exchange e Teams interagir.</a></p>
<ul>
</ul></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-with-skype-for-business-server"></a>Etapas de habilitação para organizações com Skype for Business Server  

1.  Atenda aos pré-requisitos detalhados na seção Iniciar aqui acima.

2.  Alternar o locatário para o modo Ilhas (para locatários provisionados APÓS 01/09/2019, entre em contato com o suporte para fazer essa alteração)  
    [Definir suas configurações de coexistência e atualização](setting-your-coexistence-and-upgrade-settings.md)

3.  Configurar seu locatário de acordo com as políticas de negócios/empresa da sua empresa  
    [Gerenciar as configurações do Microsoft Teams para sua organização](enable-features-office-365.md)

4.  Implantar o Teams cliente  
    [Obter clientes para o Teams](get-clients.md)

5.   Impulsionar seu programa de adoção  
    [Adotar o Microsoft Teams](adopt-microsoft-teams-landing-page.md)<br/>
    [Lista de verificação de início rápido da adoção do Microsoft Teams](teams-adoption-quick-start-checklist.md)

6.  Comece a planejar a movimentação de outras cargas de trabalho para Microsoft 365 ou Office 365

7.  Estabeleça Skype for Business híbrido e siga os caminhos de atualização recomendados para servidores Skype for Business e Lync  
    [Atualizar do Skype for Business local para o Teams](upgrade-to-teams-execute-skypeforbusinesshybridonprem.md)

## <a name="closing-statement"></a>Instrução closing

Microsoft Teams pode ser um habilitador para sua organização reunir todos os funcionários, operadores de informações e trabalhadores da linha de frente em uma única plataforma. Você pode [começar hoje](https://products.office.com/microsoft-teams/group-chat-software) . Você pode manter contato com todos os nossos comunicados mais recentes e atualizações mensais do produto [aqui](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog).

Além disso, como empresas em todo o mundo estão gerenciando a situação atual da COVID-19, criamos uma série de conteúdo que ajudará você a utilizar Teams para o impacto máximo em sua organização.

  - Nosso [compromisso com os clientes durante a COVID-19](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)

  - [2 semanas em: o que aprendemos sobre o trabalho remoto](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/18/making-the-switch-to-remote-work-5-things-weve-learned/)

  - [Entregando reuniões e eventos online](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/delivering-online-meetings-events/)

  - [Ajudar empresas pequenas e de médio porte a trabalhar remotamente com o Teams](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/helping-smb-customers-work-remotely-microsoft-teams/)

  - [Transformação digital de eventos ao vivo: observações de Bob Bejan da linha de frente](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/13/digital-transformation-live-events-bob-bejans-observations-frontline/)

  - [As 9 principais maneiras que o TI da Microsoft está possibilitando o trabalho remoto para seus funcionários](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/top-9-ways-microsoft-it-enabling-remote-work-employees/)

  - [Trabalhar remotamente, manter a segurança – dicas para CISOs](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/work-remotely-stay-secure-ciso-tips/)

  - [Ajudar professores e alunos a mudar para o aprendizado remoto](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/11/helping-teachers-students-switch-remote-learning/)

  - [Manter-se produtivo enquanto trabalha remotamente com Microsoft Teams](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/10/staying-productive-while-working-remotely-with-microsoft-teams/)

## <a name="support-services-reference"></a>Referência dos Serviços de Suporte

Teams conta com o Exchange Online, SharePoint Online, OneDrive for Business e Grupos do Microsoft 365 para fornecer aos usuários um Microsoft 365 ou Office 365 experiência. Conforme mencionado acima, o Teams funcionará sem a implantação completa desses serviços , com funcionalidades limitadas. Você pode ler mais sobre Teams e seus pré-requisitos [aqui: Bem-vindo ao Teams](teams-overview.md).

Para obter informações específicas sobre cada um dos serviços listados acima, siga os links abaixo:

  - Exchange Online é usado para recursos de calendário e armazenamento de mensagens ponto a ponto em Teams. Para saber mais, leia [Como Exchange e Teams interagir](exchange-teams-interact.md)

> [!IMPORTANT]
> Para Teams interoperabilidade com o Exchange local, você deve configurar o novo protocolo de autenticação OAuth do Exchange, conforme descrito em Configurar a autenticação [OAuth](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help) entre organizações Exchange e Exchange Online.

  - SharePoint é usado para compartilhamento de arquivos em canais, enquanto /OneDrive for Business é usado para compartilhamento de arquivos em chat em grupo ou 1:1. Para saber mais, leia [Como SharePoint Online e OneDrive for Business interagir com Microsoft Teams](sharepoint-onedrive-interact.md).

  - [Grupos do Microsoft 365](office-365-groups.md) são usados para criação/gerenciamento de equipe e canal.


## <a name="related-topics"></a>Tópicos relacionados

[Cartazes de soluções de telefonia e arquitetura de TI do Microsoft Teams](teams-architecture-solutions-posters.md#teams-as-part-of-microsoft-365)

[Planejar conectividade híbrida entre o Skype for Business Server e o Office 365](/SkypeForBusiness/hybrid/plan-hybrid-connectivity)

[Dar suporte a funcionários remotos usando Teams](support-remote-work-with-teams.md)

[Trabalhar remotamente com Microsoft 365](https://aka.ms/remote-work)
