---
title: Lançar o Microsoft Teams First
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
description: Use esta orientação para lançar o Microsoft Teams como sua primeira carga de trabalho do Microsoft 365 ou Office 365.
ROBOTS: NOINDEX, NOFOLLOW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 81ecf9a0f963a1be577149c585424c140df2abd5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119350"
---
# <a name="roll-out-microsoft-teams-first"></a>Lançar o Microsoft Teams First

O Microsoft Teams pode ajudar seus funcionários a permanecer conectados e colaborar uns com os outros, especialmente no momento atual sem precedentes em que o trabalho remoto é uma realidade de funcionários em todo o mundo. Poder conversar, fazer reuniões em vídeo e colaborar em documentos do Office no Teams pode ajudar as empresas a se manter produtivas. Se você é uma pequena empresa, uma organização sem fins lucrativos ou uma grande organização, você pode começar com o Teams como a primeira carga de trabalho no Microsoft 365 ou no pacote do Office 365 antes de implantar qualquer outro aplicativo ou serviço do Office.

Este artigo detalha as considerações que você deve fazer com a abordagem "Teams First".

> [!IMPORTANT]
> Embora o Teams possa ser a primeira carga de trabalho implantada na nuvem da sua organização, a implantação do Teams deve fazer parte da estratégia geral de implantação na nuvem.

Se você já tiver lançado outros serviços do Microsoft 365 ou Office 365 e o Teams for sua próxima carga de trabalho a ser lançado (em vez do primeiro), comece com Como lançar o [Teams](./deploy-overview.md).

## <a name="start-here"></a>Iniciar aqui

Para começar a implantação do Teams First, você precisará atender, no mínimo, a alguns pré-requisitos. A lista a seguir mostrará o que você deve ter para sua organização antes que o Teams possa ser habilitado:

1.  Uma organização do Microsoft 365 ou Office 365 configurada com seu nome de domínio

2.  Conectividade do Azure Active Directory (conexão AAD) ou solução de sincronização de identidade de nuvem semelhante – com todos os atributos necessários sincronizados com seu locatário  
    Para entender os atributos sincronizados com a sincronização do AAD, leia Sincronização do [Azure AD Connect: Atributos sincronizados com o Azure Active Directory](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)

3.  Licenças de usuário apropriadas atribuídas ao Teams  
    Para entender o licenciamento do Teams, leia a descrição [do serviço do Microsoft Teams.](/office365/servicedescriptions/teams-service-description)

4.  Rede da organização preparada para o Teams  
    Para entender a preparação da rede, leia [Preparar a rede da sua organização para o Teams.](prepare-network.md)

5.  Permitir acesso de rede ao Exchange, Sharepoint e OneDrive for Business no Microsoft 365 ou Office 365: [URLs do Office 365](/office365/enterprise/urls-and-ip-address-ranges)e intervalos de endereços IP.

> [!NOTE]
> Os locatários criados após 1º de setembro de 2019 são provisionados no modo Somente equipes.
> 
> [!IMPORTANT]
> Se você tiver o Skype for Business Server implantado e seu locatário tiver sido provisionado APÓS 1º de setembro de 2019, entre em contato com o suporte para habilitar recursos de coexistência para o Teams. Certifique-se de que sua "política de atualização de toda a organização" seja definida como "modo <span class="underline">ilha"</span> antes de atribuir licenças do Teams a um usuário.

## <a name="migration-starting-points"></a>Pontos de partida da migração

Sua jornada para o Microsoft 365 ou Office 365 e recursos disponíveis no Teams, dependendo do ponto de partida e da existência do skype for Business local ou do servidor Lync. As seções a seguir detalham recursos básicos e opções de configuração, além dos pré-requisitos acima. Nós quebramos os cenários de ponto de partida para os seguintes tópicos:

**Configuração do Tenant Teams**: Os modos de locatário e usuário são usados para controlar o comportamento do destinatário. Essas configurações podem ser atribuídas no nível do locatário ou no nível do usuário em uma organização. Para saber mais, leia [Coexistência com o Skype for Business.](coexistence-chat-calls-presence.md)

**Chat / Comunicação externa no Teams**: os serviços de chat referem-se a conversas de chat ponto a ponto ou grupo dentro e organização ou externamente à organização. A comunicação externa também é conhecida como federação no Skype for Business.

**Criar e exibir** reuniões no Teams : um usuário sempre pode criar reuniões online por meio do complemento do Outlook Teams e o discagem PSTN está disponível em todos os cenários depois que o usuário é licenciado. As informações de calendário do Teams e do Skype for Business armazenam na caixa de correio do Exchange do usuário. No local, o servidor exchange deve ser Exchange Server cu3 2016 ou superior para que o cliente do Teams possa interagir com a caixa de correio do usuário. Sem o acesso à caixa de correio do Exchange, o ícone Calendário no Teams não será exibido e o usuário não poderá exibir, criar ou modificar reuniões no cliente do Teams.

**Recursos de chamada VoIP/PSTN no Teams**: Chamar pode ser Voz sobre IP (VoIP) ou Rede Telefônica Pública Comugada (PSTN). A conectividade VoIP acontece na verdade entre clientes do Teams, enquanto a conectividade PSTN acontece quando um usuário disca um número de telefone externo.  

O Teams suporta dois tipos de conectividade PSTN. Plano de Chamadas da Microsoft, quando a Microsoft fornece infraestrutura de telefonia, incluindo o número de telefone para um usuário ou configuração de Roteamento Direto, onde o cliente fornece a conectividade de telefonia por meio de um Controlador de Borda de Sessão (SBC) para o usuário do Teams.  
Para saber mais, leia [Qual Plano de Chamadas é o certo para você?](calling-plan-landing-page.md) e [Roteamento Direto do Sistema de Telefonia.](direct-routing-landing-page.md)

**Colaboração de equipes** e canais no Teams : no Teams, as equipes são grupos de pessoas reunidas para trabalho, projetos ou interesses comuns. As equipes são feitas de canais. Cada canal é criado em torno de um tópico, como "Eventos de Equipe", um nome de departamento ou apenas por diversão. Canais são onde você faz reuniões, conversa e trabalha em arquivos juntos. Durante a colaboração

OneDrive for Business (compartilhamento de arquivos **P2P)** no Teams : fora do Teams e canais, os usuários do Teams podem compartilhar arquivos ponto a ponto usando o OneDrive for business ou outros programas de arquivo de compartilhamento P2P, como Arquivos Citrix, DropBox, Box e Google Drive. Para o OneDrive for Business, um usuário deve ter a licença do SharePoint Online atribuída.

**Plataforma de** Aplicativos : os aplicativos fornecem ferramentas in-locar para sua organização obter mais do Teams. Esses aplicativos combinam a funcionalidade de guias, extensões de mensagens, conectores e bots fornecidos pela Microsoft, construídos por terceiros ou por desenvolvedores em sua organização.

**Recursos de segurança e conformidade:** O Teams tem uma ampla variedade de informações para ajudá-lo com áreas de conformidade, incluindo políticas de retenção, Proteção contra Perda de Dados (DLP), Descoberta e retenção legal para canais, chats e arquivos, pesquisa de log de auditoria. Para saber mais, leia [Segurança e conformidade no Microsoft Teams.](security-compliance-overview.md)  

> [!NOTE]
> Os recursos avançados de Descoberta Desdiscovery exigem licenciamento do E5.

[Comparar opções de licenciamento](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).

Leia [Como o Exchange e o Microsoft Teams interagem](exchange-teams-interact.md) para saber quais recursos de conformidade estão disponíveis em seu cenário.

## <a name="organizations-span-classunderlinewithoutspan-skype-for-business-or-lync-server"></a>Organizações **<span class="underline">sem</span>** Skype for Business ou Lync Server

Esse ponto de partida supõe que sua organização não usa o Skype for Business ou o Lync Server no momento e o Teams será seu primeiro aplicativo no Microsoft 365 ou Office 365. A tabela a seguir detalha a configuração de alto nível e os recursos de usuário final do Teams para serviços principais.

<table>
<thead>
<tr class="header">
<th>Item</th>
<th>Observações</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Configuração do Tenant Teams</td>
<td>Modo Somente equipes, todos os recursos de chat e chamada estão somente no Teams.</td>
</tr>
<tr class="even">
<td>Chat/Comunicação Externa no Teams</td>
<td><p>Interna (dentro da organização do Microsoft 365 ou office 365) e comunicação de chat externo possível do Teams.</p>
<p><em>Observação: as entradas DNS devem ser configuradas para acesso externo. Os registros DNS do Skype for Business são necessários mesmo que você não tenha o Skype for Business local ou no Microsoft 365 ou Office 365, para permitir a federação com ambientes do Lync e do Skype for Business:<br />
<a href="/office365/enterprise/external-domain-name-system-records">Registros do Sistema de Nomes de Domínio Externo</a></em></p></td>
</tr>
<tr class="odd">
<td>Criar e exibir reuniões no Teams</td>
<td><p>Capaz de criar reuniões internas e externas por meio do complemento do Outlook.</p>
<p>O recurso Discagem PSTN e Discagem está disponível com as licenças de Audioconferência.</p>
<p>O acesso ao calendário do Teams requer o Exchange 2016 CU3+ local implantado com o Exchange híbrido estabelecido: Criar uma implantação híbrida com o <a href="/exchange/hybrid-deployment/deploy-hybrid">assistente de Configuração Híbrida.</a> </p>
<p>Além da configuração híbrida do Exchange, estabeleça a autenticação OAuth do Exchange: <a href="https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help"> Configure OAuth authentication between Exchange and Exchange Online organizations".</p>

</p></td>
</tr>
<tr class="even">
<td>Recursos de chamada<br />
VoIP/PSTN no Teams</td>
<td><p>VoIP interna e externamente para o locatário está disponível.</p>
<p>Os serviços PSTN podem ser configurados por meio do Microsoft Phone System, além de adicionar um Plano de Chamadas da Microsoft ou Roteamento Direto.</p></td>
</tr>
<tr class="odd">
<td>Colaboração de equipes e canais no Teams</td>
<td><p>Para ter uma experiência completa, incluindo recursos de conformidade, uma licença do SharePoint Online precisa ser atribuída ao usuário.</p>
<p>A migração de sites locais existentes do SharePoint não é necessária.</p></td>
</tr>
<tr class="even">
<td>OneDrive for Business (compartilhamento de arquivos P2P)</td>
<td>O OneDrive for Business exige que um usuário tenha uma licença do SharePoint Online atribuída. Sem essa licença, o compartilhamento de arquivos ponto a ponto não será possível.</td>
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
<p>Conjunto de recursos completo disponível com o Exchange Online; O Exchange local oferece suporte à maioria desses recursos. Para ver uma lista completa, consulte <a href="/MicrosoftTeams/exchange-teams-interact">Como o Exchange e o Teams interagem.</a></p></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-without-skype-for-business-or-lync-server"></a>Etapas de habilitação para organizações sem Skype for Business ou Lync Server

1.  Atender pré-requisitos detalhados na seção Iniciar aqui acima

2.  Alternar locatário para o modo Somente do Teams (somente para locatários [existentes): Definindo suas configurações de coexistência e atualização.](setting-your-coexistence-and-upgrade-settings.md)

3.  Configure seu locatário de acordo com as políticas de negócios/empresa da sua empresa: Gerenciar as configurações do [Microsoft Teams para sua organização.](enable-features-office-365.md)

4.  Implantar o cliente do Teams para seus usuários: [Obter clientes para o Teams](get-clients.md)

5.  Conduzir seu programa de adoção  
    [Adotar o Microsoft Teams](adopt-microsoft-teams-landing-page.md)
    
    [Lista de verificação de início rápido da adoção do Microsoft Teams](teams-adoption-quick-start-checklist.md)

6.  Comece a planejar a movimentação de outras cargas de trabalho para o Microsoft 365 ou Office 365

## <a name="organizations-span-classunderlinewithspan-skype-for-business-or-lync-server"></a>Organizações **<span class="underline">com</span>** o Skype for Business ou o servidor Lync

Esse ponto de partida supõe que sua organização utilize o servidor do Skype for Business 2019 ou 2015+ ou do Lync 2013+ no local. Já temos orientações abrangentes para as organizações migrarem de servidores locais para o Teams e isso deve ser seguido para esses cenários. Essa orientação é específica para o cenário em que o Teams é o primeiro aplicativo que você usa no Microsoft 365 ou no Office 365. A tabela a seguir detalha a configuração de alto nível e os recursos de usuário final do Teams para serviços principais.

<table>
<thead>
<tr class="header">
<th>Item</th>
<th>Observações</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Configuração do Tenant Teams</td>
<td>Modo de ilhas.</td>
</tr>
<tr class="even">
<td>Chat/Comunicação Externa no Teams</td>
<td>Interna somente em seu próprio locatário, a comunicação externa (federação) é por meio da implantação do servidor skype for Business ou do Lync.</td>
</tr>
<tr class="odd">
<td>Criar e exibir reuniões no Teams</td>
<td><p>Capaz de criar reuniões internas e externas por meio do complemento do Outlook.</p>
<p>O recurso Discagem PSTN e Discagem está disponível com as licenças de Audioconferência.</p>
<p>O acesso ao calendário do Teams requer o Exchange 2016 CU3+ local implantado com o Exchange híbrido estabelecido:<br />
<a href="/exchange/hybrid-deployment/deploy-hybrid">Crie uma implantação híbrida com o assistente de Configuração Híbrida.</a></p>
<p>O administrador pode controlar o complemento do Skype for Business Outlook por meio do atributo PreferredMeetingProviderForIslandsMode da política de reunião do Teams:<a href="/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps"> set-csteamsmeetingpolicy</a>.</p> 
</td>
</tr>
<tr class="even">
<td>Recursos de chamada<br />
VoIP/PSTN no Teams</td>
<td><p>O VoIP internamente para o locatário está disponível.</p>
<p>Os serviços PSTN ou Plano de Chamada não estarão disponíveis até que o usuário seja movido para a experiência Somente do Teams.</p></td>
</tr>
<tr class="odd">
<td>Colaboração de equipes e canais no Teams</td>
<td><p>Para ter uma experiência completa, incluindo recursos de conformidade, uma licença do SharePoint Online precisa ser atribuída ao usuário.</p>
<p>A migração de sites locais existentes do SharePoint não é necessária.</p></td>
</tr>
<tr class="even">
<td>OneDrive for Business (compartilhamento de arquivos P2P)</td>
<td>O OneDrive for Business exige que um usuário tenha uma licença do SharePoint Online atribuída. Sem essa licença, o compartilhamento de arquivos ponto a ponto não será possível.</td>
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
<p>Conjunto de recursos completo disponível com o Exchange Online; O Exchange local oferece suporte à maioria desses recursos. Para uma lista completa, consulte <a href="/MicrosoftTeams/exchange-teams-interact">Como o Exchange e o Teams interagem.</a></p>
<ul>
</ul></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-with-skype-for-business-server"></a>Etapas de habilitação para organizações com o Skype for Business Server  

1.  Atender a pré-requisitos detalhados na seção Iniciar aqui acima.

2.  Alternar locatário para o modo Ilhas (para locatários provisionados APÓS 1/9/2019, entre em contato com o suporte para fazer essa alteração)  
    [Definir suas configurações de coexistência e atualização](setting-your-coexistence-and-upgrade-settings.md)

3.  Configurar seu locatário de acordo com as políticas de negócios/empresa da sua empresa  
    [Gerenciar as configurações do Microsoft Teams para sua organização](enable-features-office-365.md)

4.  Implantar o cliente do Teams  
    [Obter clientes para o Teams](get-clients.md)

5.   Conduzir seu programa de adoção  
    [Adotar o Microsoft Teams](adopt-microsoft-teams-landing-page.md)<br/>
    [Lista de verificação de início rápido da adoção do Microsoft Teams](teams-adoption-quick-start-checklist.md)

6.  Comece a planejar a movimentação de outras cargas de trabalho para o Microsoft 365 ou Office 365

7.  Estabeleça o Skype for Business híbrido e siga os caminhos de atualização recomendados para servidores Skype for Business e Lync  
    [Atualizar do Skype for Business local para o Teams](upgrade-to-teams-execute-skypeforbusinesshybridonprem.md)

## <a name="closing-statement"></a>Instrução Closing

O Microsoft Teams pode ser um habilitador para sua organização reunir todos os funcionários, funcionários de informações e funcionários da Linha de Frente em uma única plataforma. Você pode [começar hoje.](https://products.office.com/microsoft-teams/group-chat-software) Você pode manter contato com todos os nossos comunicados mais recentes e atualizações mensais de produtos [aqui](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog).

Além disso, como as empresas em todo o mundo estão gerenciando a situação atual do COVID-19, criamos uma série de conteúdos que ajudarão você a utilizar o Teams para o impacto máximo em sua organização.

  - Nosso [compromisso com os clientes durante o COVID-19](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)

  - [2 semanas em: o que aprendemos sobre o trabalho remoto](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/18/making-the-switch-to-remote-work-5-things-weve-learned/)

  - [Entrega de reuniões e eventos online](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/delivering-online-meetings-events/)

  - [Ajudar empresas pequenas e de médio porte a trabalhar remotamente com o Teams](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/helping-smb-customers-work-remotely-microsoft-teams/)

  - [Transformação digital de eventos ao vivo: observações de Bob Bejan da linha de frente](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/13/digital-transformation-live-events-bob-bejans-observations-frontline/)

  - [As 9 principais maneiras que o TI da Microsoft está possibilitando o trabalho remoto para seus funcionários](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/top-9-ways-microsoft-it-enabling-remote-work-employees/)

  - [Trabalhar remotamente, manter-se seguro– dicas para CISOs](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/work-remotely-stay-secure-ciso-tips/)

  - [Ajudar professores e alunos a mudar para o aprendizado remoto](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/11/helping-teachers-students-switch-remote-learning/)

  - [Manter-se produtivo enquanto trabalha remotamente com o Microsoft Teams](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/10/staying-productive-while-working-remotely-with-microsoft-teams/)

## <a name="support-services-reference"></a>Referência dos Serviços de Suporte

O Teams depende do Exchange Online, do SharePoint Online, do OneDrive for Business e dos Grupos do Microsoft 365 para fornecer aos usuários uma experiência totalmente integrada do Microsoft 365 ou do Office 365. Conforme mencionado acima, o Teams funcionará sem a implantação completa desses serviços – com recursos limitados. Você pode ler mais sobre o Teams e seus pré-requisitos aqui: [Bem-vindo ao Teams](teams-overview.md).

Para detalhes sobre cada um dos serviços listados acima, siga os links abaixo:

  - O Exchange Online é usado para recursos de calendário e armazenamento de mensagens ponto a ponto no Teams. Para saber mais, leia [Como o Exchange e o Teams interagem](exchange-teams-interact.md)

> [!IMPORTANT]
> Para a interopção do Teams com o Exchange local, você deve configurar o novo protocolo de autenticação OAuth do Exchange, conforme descrito em [Configure OAuth authentication between Exchange and Exchange Online organizations](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help).

  - O SharePoint é usado para compartilhamento de arquivos em canais, enquanto /OneDrive for Business é usado para compartilhamento de arquivos em 1:1 ou chat em grupo. Para saber mais, leia [Como o SharePoint Online e o OneDrive for Business interagem com o Microsoft Teams.](sharepoint-onedrive-interact.md)

  - [Os Grupos do Microsoft 365](office-365-groups.md) são usados para criação/gerenciamento de equipe e canal.


## <a name="related-topics"></a>Tópicos relacionados

[Cartazes de soluções de telefonia e arquitetura de TI do Microsoft Teams](teams-architecture-solutions-posters.md#teams-as-part-of-microsoft-365)

[Planejar conectividade híbrida entre o Skype for Business Server e o Office 365](/SkypeForBusiness/hybrid/plan-hybrid-connectivity)

[Dar suporte a funcionários remotos usando o Teams](support-remote-work-with-teams.md)

[Trabalhar remotamente com o Microsoft 365](https://aka.ms/remote-work)