---
title: Roll out Microsoft Teams First
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
description: Use essas diretrizes para lançar Microsoft Teams como sua primeira carga de trabalho Microsoft 365 ou Office 365 primeira.
ROBOTS: NOINDEX, NOFOLLOW
appliesto:
- Microsoft Teams
ms.openlocfilehash: ddc107db668a582ad164e20f3b3ded169bd5d86125d949fe45d4d2f89090a8f7
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54312569"
---
# <a name="roll-out-microsoft-teams-first"></a>Roll out Microsoft Teams First

Microsoft Teams pode ajudar seus funcionários a permanecer conectados e colaborar uns com os outros, especialmente no momento atual sem precedentes em que o trabalho remoto é uma realidade de funcionários em todo o mundo. Poder conversar, fazer reuniões em vídeo e colaborar em Office documentos dentro Teams pode ajudar as empresas a se manter produtivas. Se você é uma pequena empresa, uma organização sem fins lucrativos ou uma grande, você pode começar com o Teams como a primeira carga de trabalho no Microsoft 365 ou no pacote Office 365 antes de implantar qualquer outro Aplicativo do Office ou serviço.

Este artigo detalha as considerações que você deve fazer com a abordagem "Teams Primeiro".

> [!IMPORTANT]
> Embora Teams possa ser a primeira carga de trabalho implantada na nuvem da sua organização, a implantação Teams deve fazer parte da estratégia geral de implantação na nuvem.

Se você já tiver lançado outros serviços Microsoft 365 ou Office 365 e Teams for sua próxima carga de trabalho a ser rolada (em vez da primeira), comece com [Como](./deploy-overview.md)lançar Teams .

## <a name="start-here"></a>Iniciar aqui

Para começar a Teams primeira implantação, você precisará atender, no mínimo, a alguns pré-requisitos. A lista a seguir mostrará o que você deve ter para sua organização antes que Teams possa ser habilitado:

1.  Uma Microsoft 365 ou Office 365 configurada com seu nome de domínio

2.  Azure Active Directory conectividade (conexão AAD) ou solução de sincronização de identidade de nuvem semelhante – com todos os atributos necessários sincronizados com seu locatário  
    Para entender os atributos sincronizados com a sincronização do AAD, leia [Azure AD Conexão sincronização:](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized) Atributos sincronizados com Azure Active Directory

3.  Licenças de usuário apropriadas atribuídas Teams  
    Para entender Teams licenciamento, leia [Microsoft Teams descrição do serviço.](/office365/servicedescriptions/teams-service-description)

4.  Rede da organização preparada para Teams  
    Para entender a preparação da rede, leia [Prepare your organization's network for Teams](prepare-network.md).

5.  Permitir acesso à rede Exchange, Sharepoint e OneDrive for Business em Microsoft 365 ou Office 365: [Office 365 URLs e intervalos de endereços IP](/office365/enterprise/urls-and-ip-address-ranges).

> [!NOTE]
> Os locatários criados após 1º de setembro de 2019 são provisionados Teams modo Somente.
> 
> [!IMPORTANT]
> Se você tiver Skype for Business Server implantado e seu locatário tiver sido provisionado APÓS 1º de setembro de 2019, entre em contato com o suporte para habilitar recursos de coexistência para Teams. Certifique-se de que sua "política de atualização de toda a organização" seja definida como "modo <span class="underline">ilha"</span> antes de atribuir Teams licenças a um usuário.

## <a name="migration-starting-points"></a>Pontos de partida da migração

Sua jornada para Microsoft 365 ou Office 365 recursos disponíveis no Teams, dependendo do ponto de partida e da existência do servidor local Skype for Business ou Lync. As seções a seguir detalham recursos básicos e opções de configuração, além dos pré-requisitos acima. Nós quebramos os cenários de ponto de partida para os seguintes tópicos:

**Configuração Teams locatário**: Os modos de locatário e usuário são usados para controlar o comportamento do destinatário. Essas configurações podem ser atribuídas no nível do locatário ou no nível do usuário em uma organização. Para saber mais, leia [Coexistência com Skype for Business](coexistence-chat-calls-presence.md).

**Chat / Comunicação externa no Teams:** Os serviços de chat referem-se a conversas de chat ponto a ponto ou grupo dentro e organização ou externamente à organização. A comunicação externa também é chamada de federação no Skype for Business.

Criar e exibir reuniões em **Teams:** um usuário sempre pode criar reuniões online por meio do Outlook Teams e o discagem PSTN estará disponível em todos os cenários depois que o usuário for licenciado. Teams e Skype for Business de calendário na caixa de correio de Exchange do usuário. No local, Exchange servidor deve ser Exchange Server 2016 CU3 ou superior para que o cliente Teams possa interagir com a caixa de correio do usuário. Sem Exchange caixa de correio acessar o ícone Calendário no Teams não aparecerá e o usuário não poderá exibir, criar ou modificar reuniões no cliente Teams.

**Recursos de chamada VoIP/PSTN no Teams:** a chamada pode ser VoIP (Voz sobre IP) ou PSTN (Rede Telefônica Pública Comugada). A conectividade VoIP acontece de forma nativa entre Teams clientes, enquanto a conectividade PSTN acontece quando um usuário disca um número de telefone externo.  

Teams suporte a dois tipos de conectividade PSTN. Plano de Chamadas da Microsoft, quando a Microsoft fornece infraestrutura de telefonia, incluindo o número de telefone para um usuário ou configuração de Roteamento Direto, em que o cliente fornece a conectividade de telefonia por meio de um Controlador de Borda de Sessão (SBC) para o usuário Teams de sessão.  
Para saber mais, leia [Qual Plano de Chamadas é o certo para você?](calling-plan-landing-page.md) e Sistema de Telefonia [Roteamento Direto.](direct-routing-landing-page.md)

**Teams e colaboração de** canais em Teams : no Teams, as equipes são grupos de pessoas reunidas para trabalho, projetos ou interesses comuns. Teams são feitos de canais. Cada canal é criado em torno de um tópico, como "Eventos de Equipe", um nome de departamento ou apenas por diversão. Canais são onde você faz reuniões, conversa e trabalha em arquivos juntos. Durante a colaboração

OneDrive for Business (compartilhamento de arquivos **P2P)** no Teams: fora do Teams e canais, os usuários do Teams podem compartilhar arquivos ponto a ponto usando o OneDrive para empresas ou outros programas de arquivo de compartilhamento P2P, como Arquivos Citrix, DropBox, Box e Google Drive. Para OneDrive para empresas, um usuário deve ter uma licença SharePoint Online atribuída.

**Plataforma de** Aplicativos : os aplicativos fornecem ferramentas in-locar para que sua organização receba mais informações Teams. Esses aplicativos combinam a funcionalidade de guias, extensões de mensagens, conectores e bots fornecidos pela Microsoft, construídos por terceiros ou por desenvolvedores em sua organização.

Recursos de segurança e **conformidade:** o Teams tem uma ampla variedade de informações para ajudá-lo com áreas de conformidade, incluindo políticas de retenção, Proteção contra Perda de Dados (DLP), Descoberta e retenção legal para canais, chats e arquivos, pesquisa de log de auditoria. Para saber mais, leia [Segurança e conformidade em Microsoft Teams](security-compliance-overview.md).  

> [!NOTE]
> Os recursos avançados de Descoberta Desdiscovery exigem licenciamento do E5.

[Comparar opções de licenciamento](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).

Leia [Como Exchange e Microsoft Teams interagir](exchange-teams-interact.md) para saber quais recursos de conformidade estão disponíveis em seu cenário.

## <a name="organizations-span-classunderlinewithoutspan-skype-for-business-or-lync-server"></a>Organizações **<span class="underline">sem</span>** Skype for Business ou Lync Server

Esse ponto de partida supõe que sua organização não usa o Skype for Business ou o Lync Server no momento e Teams será seu primeiro aplicativo no Microsoft 365 ou Office 365. A tabela a seguir detalha a configuração de alto nível e os recursos do usuário final para Teams para serviços principais.

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
<td>Teams Somente modo, todos os recursos de chat e chamada estão Teams Somente.</td>
</tr>
<tr class="even">
<td>Chat/Comunicação Externa no Teams</td>
<td><p>Interna (dentro Microsoft 365 ou Office 365) e comunicação de chat externo possível a partir Teams.</p>
<p><em>Observação: as entradas DNS devem ser configuradas para acesso externo. Skype for Business Os registros DNS são necessários mesmo que você não tenha Skype for Business local ou no Microsoft 365 ou Office 365, para permitir a federação com o Lync e Skype for Business ambientes:<br />
<a href="/office365/enterprise/external-domain-name-system-records">Registros do Sistema de Nomes de Domínio Externo</a></em></p></td>
</tr>
<tr class="odd">
<td>Criar e exibir reuniões em Teams</td>
<td><p>Capaz de criar reuniões internas e externas Outlook um complemento.</p>
<p>O recurso Discagem PSTN e Discagem está disponível com as licenças de Audioconferência.</p>
<p>Teams de calendário requer Exchange cu3+ 2016 local implantado com Exchange híbrido estabelecido: Criar uma implantação híbrida com o assistente de Configuração <a href="/exchange/hybrid-deployment/deploy-hybrid">Híbrida.</a> </p>

Além de Exchange configuração híbrida, estabeleça uma autenticação OAuth Exchange: Configurar a autenticação [OAuth](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)entre Exchange e Exchange Online organizações . 

</p></td>
</tr>
<tr class="even">
<td>Recursos de chamada<br />
VoIP/PSTN no Teams</td>
<td><p>VoIP interna e externamente para o locatário está disponível.</p>
<p>Os serviços PSTN podem ser configurados por meio Telefone Microsoft System, além de adicionar um Plano de Chamadas da Microsoft ou Roteamento Direto.</p></td>
</tr>
<tr class="odd">
<td>Teams e colaboração de canais Teams</td>
<td><p>Para ter uma experiência completa, incluindo recursos de conformidade, uma licença SharePoint Online precisa ser atribuída ao usuário.</p>
<p>A migração de sites SharePoint locais existentes não é necessária.</p></td>
</tr>
<tr class="even">
<td>OneDrive for Business (compartilhamento de arquivos P2P)</td>
<td>OneDrive for Business requer que um usuário tenha uma licença SharePoint Online atribuída. Sem essa licença, o compartilhamento de arquivos ponto a ponto não será possível.</td>
</tr>
<tr class="odd">
<td>Plataforma de aplicativos</td>
<td>Os usuários poderão usar os aplicativos designados disponíveis para eles de acordo com as políticas da sua empresa.<br />
Saiba mais aqui: <a href="/microsoftteams/admin-settings">Configurações de administrador para aplicativos no Teams</a></td>
</tr>
<tr class="even">
<td>Recursos de segurança e conformidade</td>
<td><ul>
<li><p>As políticas de retenção estão disponíveis.</p></li>
<li><p>Há suporte para a Descoberta EDiscovery e a Responsabilidade Legal para conformidade em mensagens de canal.</p></li>
<li><p>As políticas de Prevenção contra Perda de Dados (DLP) estão disponíveis.</p></li>
</ul>
<p>Conjunto de recursos completo disponível com Exchange Online; Exchange local oferece suporte à maioria desses recursos. Para ver uma lista completa, consulte <a href="/MicrosoftTeams/exchange-teams-interact">How Exchange and Teams interact</a>.</p></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-without-skype-for-business-or-lync-server"></a>Etapas de habilitação para organizações sem Skype for Business ou Lync Server

1.  Atender pré-requisitos detalhados na seção Iniciar aqui acima

2.  Alternar locatário para Teams modo Somente (somente para locatários existentes): Definindo suas [configurações de coexistência e atualização.](setting-your-coexistence-and-upgrade-settings.md)

3.  Configure seu locatário de acordo com as políticas de negócios/empresa da sua empresa: Gerenciar Microsoft Teams [configurações da sua organização.](enable-features-office-365.md)

4.  Implantar o Teams cliente para seus usuários: [Obter clientes para Teams](get-clients.md)

5.  Conduzir seu programa de adoção  
    [Adotar o Microsoft Teams](adopt-microsoft-teams-landing-page.md)
    
    [Lista de verificação de início rápido da adoção do Microsoft Teams](teams-adoption-quick-start-checklist.md)

6.  Comece a planejar a movimentação de outras cargas de trabalho para Microsoft 365 ou Office 365

## <a name="organizations-span-classunderlinewithspan-skype-for-business-or-lync-server"></a>Organizações **<span class="underline">com</span>** Skype for Business ou servidor Lync

Esse ponto de partida supõe que sua organização utiliza o servidor Skype for Business 2019 ou 2015+ ou Lync 2013+ no local. Já temos orientações abrangentes para as organizações migrarem de servidores locais para Teams e devem ser seguidas para esses cenários. Essa orientação é específica para o cenário em que Teams é o primeiro aplicativo que você usa no Microsoft 365 ou Office 365. A tabela a seguir detalha a configuração de alto nível e os recursos do usuário final para Teams para serviços principais.

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
<td>Modo de ilhas.</td>
</tr>
<tr class="even">
<td>Chat/Comunicação Externa no Teams</td>
<td>Interna somente em seu próprio locatário, a comunicação externa (federação) é por meio da implantação do Skype for Business ou do servidor Lync.</td>
</tr>
<tr class="odd">
<td>Criar e exibir reuniões em Teams</td>
<td><p>Capaz de criar reuniões internas e externas Outlook um complemento.</p>
<p>O recurso Discagem PSTN e Discagem está disponível com as licenças de Audioconferência.</p>
<p>Teams acesso ao calendário requer Exchange 2016 CU3+ local implantado com Exchange híbrido estabelecido:<br />
<a href="/exchange/hybrid-deployment/deploy-hybrid">Crie uma implantação híbrida com o assistente de Configuração Híbrida.</a></p>
<p>O administrador pode controlar o Skype for Business Outlook do Teams por meio do atributo PreferredMeetingProviderForIslandsMode da política de reunião do Teams:<a href="/powershell/module/skype/set-csteamsmeetingpolicy"> set-csteamsmeetingpolicy</a>.</p> 
</td>
</tr>
<tr class="even">
<td>Recursos de chamada<br />
VoIP/PSTN no Teams</td>
<td><p>O VoIP internamente para o locatário está disponível.</p>
<p>Os serviços PSTN ou Plano de Chamada não estarão disponíveis até que o usuário seja movido para Teams somente experiência.</p></td>
</tr>
<tr class="odd">
<td>Teams e colaboração de canais Teams</td>
<td><p>Para ter uma experiência completa, incluindo recursos de conformidade, uma licença SharePoint Online precisa ser atribuída ao usuário.</p>
<p>A migração de sites SharePoint locais existentes não é necessária.</p></td>
</tr>
<tr class="even">
<td>OneDrive for Business (compartilhamento de arquivos P2P)</td>
<td>OneDrive for Business requer que um usuário tenha uma licença SharePoint Online atribuída. Sem essa licença, o compartilhamento de arquivos ponto a ponto não será possível.</td>
</tr>
<tr class="odd">
<td>Plataforma de aplicativos</td>
<td>Os usuários poderão usar os aplicativos designados disponíveis para eles de acordo com as políticas da sua empresa.<br />
Saiba mais aqui: <a href="/microsoftteams/admin-settings">Configurações de administrador para aplicativos no Teams</a></td>
</tr>
<tr class="even">
<td>Recursos de segurança e conformidade</td>
<td><ul>
<li><p>As políticas de retenção estão disponíveis.</p></li>
<li><p>Há suporte para a Descoberta EDiscovery e a Responsabilidade Legal para conformidade em mensagens de canal.</p></li>
<li><p>As políticas de Prevenção contra Perda de Dados (DLP) estão disponíveis.</p></li>
</ul>
<p>Conjunto de recursos completo disponível com Exchange Online; Exchange local oferece suporte à maioria desses recursos. Para uma lista completa, consulte <a href="/MicrosoftTeams/exchange-teams-interact">How Exchange and Teams interact.</a></p>
<ul>
</ul></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-with-skype-for-business-server"></a>Etapas de habilitação para organizações com Skype for Business Server  

1.  Atender a pré-requisitos detalhados na seção Iniciar aqui acima.

2.  Alternar locatário para o modo Ilhas (para locatários provisionados APÓS 1/9/2019, entre em contato com o suporte para fazer essa alteração)  
    [Definir suas configurações de coexistência e atualização](setting-your-coexistence-and-upgrade-settings.md)

3.  Configurar seu locatário de acordo com as políticas de negócios/empresa da sua empresa  
    [Gerenciar as configurações do Microsoft Teams para sua organização](enable-features-office-365.md)

4.  Implantar o Teams cliente  
    [Obter clientes para o Teams](get-clients.md)

5.   Conduzir seu programa de adoção  
    [Adotar o Microsoft Teams](adopt-microsoft-teams-landing-page.md)<br/>
    [Lista de verificação de início rápido da adoção do Microsoft Teams](teams-adoption-quick-start-checklist.md)

6.  Comece a planejar a movimentação de outras cargas de trabalho para Microsoft 365 ou Office 365

7.  Estabeleça Skype for Business híbrido e siga os caminhos de atualização recomendados para servidores Skype for Business e Lync  
    [Atualizar do Skype for Business local para o Teams](upgrade-to-teams-execute-skypeforbusinesshybridonprem.md)

## <a name="closing-statement"></a>Instrução Closing

Microsoft Teams pode ser um habilitador para sua organização reunir todos os funcionários, funcionários da informação e funcionários da Linha de Frente em uma única plataforma. Você pode [começar hoje.](https://products.office.com/microsoft-teams/group-chat-software) Você pode manter contato com todos os nossos comunicados mais recentes e atualizações mensais de produtos [aqui](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog).

Além disso, à medida que as empresas em todo o mundo gerenciam a situação atual do COVID-19, criamos uma série de conteúdos que o ajudarão a utilizar o Teams para o impacto máximo em sua organização.

  - Nosso [compromisso com os clientes durante o COVID-19](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)

  - [2 semanas em: o que aprendemos sobre o trabalho remoto](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/18/making-the-switch-to-remote-work-5-things-weve-learned/)

  - [Entrega de reuniões e eventos online](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/delivering-online-meetings-events/)

  - [Ajudar empresas pequenas e de médio porte a trabalhar remotamente com o Teams](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/helping-smb-customers-work-remotely-microsoft-teams/)

  - [Transformação digital de eventos ao vivo: observações de Bob Bejan da linha de frente](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/13/digital-transformation-live-events-bob-bejans-observations-frontline/)

  - [As 9 principais maneiras que o TI da Microsoft está possibilitando o trabalho remoto para seus funcionários](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/top-9-ways-microsoft-it-enabling-remote-work-employees/)

  - [Trabalhar remotamente, manter-se seguro– dicas para CISOs](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/work-remotely-stay-secure-ciso-tips/)

  - [Ajudar professores e alunos a mudar para o aprendizado remoto](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/11/helping-teachers-students-switch-remote-learning/)

  - [Manter-se produtivo enquanto trabalha remotamente com Microsoft Teams](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/10/staying-productive-while-working-remotely-with-microsoft-teams/)

## <a name="support-services-reference"></a>Referência dos Serviços de Suporte

Teams conta com grupos Exchange Online, SharePoint Online, OneDrive for Business e Microsoft 365 para fornecer aos usuários uma experiência de Microsoft 365 ou Office 365 integrada. Conforme mencionado acima, Teams funcionará sem a implantação completa desses serviços – com recursos limitados. Você pode ler mais sobre Teams e seus pré-requisitos aqui: [Bem-vindo ao Teams](teams-overview.md).

Para detalhes sobre cada um dos serviços listados acima, siga os links abaixo:

  - Exchange Online é usado para recursos de calendário e armazenamento de mensagens ponto a ponto em Teams. Para saber mais, leia [Como Exchange e Teams interagir](exchange-teams-interact.md)

> [!IMPORTANT]
> Para Teams a Exchange local, você deve configurar o novo protocolo de autenticação OAuth do Exchange conforme descrito em [Configure OAuth authentication](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)between Exchange and Exchange Online organizations .

  - SharePoint é usado para compartilhamento de arquivos em canais, enquanto /OneDrive for Business é usado para compartilhamento de arquivos em 1:1 ou chat em grupo. Para saber mais, leia [How SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).

  - [Microsoft 365 Grupos](office-365-groups.md) são usados para criação/gerenciamento de equipe e canal.


## <a name="related-topics"></a>Tópicos relacionados

[Cartazes de soluções de telefonia e arquitetura de TI do Microsoft Teams](teams-architecture-solutions-posters.md#teams-as-part-of-microsoft-365)

[Planejar conectividade híbrida entre o Skype for Business Server e o Office 365](/SkypeForBusiness/hybrid/plan-hybrid-connectivity)

[Dar suporte a funcionários remotos usando Teams](support-remote-work-with-teams.md)

[Trabalhar remotamente com Microsoft 365](https://aka.ms/remote-work)
