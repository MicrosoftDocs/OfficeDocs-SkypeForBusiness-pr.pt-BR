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
description: Use esta orientação para lançar o Microsoft Teams como sua primeira carga de trabalho do Microsoft 365 ou do Office 365.
ROBOTS: NOINDEX, NOFOLLOW
appliesto:
- Microsoft Teams
ms.openlocfilehash: a30d5bed9443df3077ab7384cd8266d2f049148d
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909475"
---
# <a name="roll-out-microsoft-teams-first"></a>Lançar o Microsoft Teams First

O Microsoft Teams pode ajudar seus funcionários a se manterem conectados e colaborarem entre si, especialmente no momento atual em que o trabalho remoto é uma realidade de funcionários em todo o mundo. Poder conversar, fazer reuniões com vídeo e colaborar em documentos do Office no Teams pode ajudar as empresas a se manterem produtivas. Se você é uma pequena empresa, sem fins lucrativos ou uma organização de grande porte, pode começar a usar o Teams como a primeira carga de trabalho no microsoft 365 ou no pacote do Office 365 antes de implantar qualquer outro aplicativo ou serviço do Office.

Este artigo detalha as considerações que você deve fazer com a abordagem "Teams First".

> [!IMPORTANT]
> Embora o Teams possa ser a primeira carga de trabalho implantada na nuvem da sua organização, a implantação do Teams deve fazer parte da sua estratégia geral de implantação na nuvem.

Se você já tiver lançado outros serviços do Microsoft 365 ou office 365 e o Teams for sua próxima carga de trabalho a ser lançado (em vez da primeira), comece com Como lançar o [Teams.](How-to-roll-out-teams.md)

## <a name="start-here"></a>Comece aqui

Para começar a implantação do Teams First, você precisará atender pelo menos alguns pré-requisitos. A lista a seguir mostrará o que você deve ter no lugar para sua organização antes que o Teams possa ser habilitado:

1.  Uma organização do Microsoft 365 ou do Office 365 configurada com seu nome de domínio

2.  Conectividade do Azure Active Directory (conexão AAD) ou solução de sincronização de identidade de nuvem semelhante, com todos os atributos necessários sincronizados com seu locatário  
    Para entender os atributos sincronizados com a sincronização do AAD, leia a sincronização do [Azure AD Connect:](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized) Atributos sincronizados com o Azure Active Directory

3.  Licenças de usuário apropriadas atribuídas ao Teams  
    Para entender o licenciamento do Teams, leia a descrição [do serviço do Microsoft Teams.](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)

4.  Rede da organização preparada para o Teams  
    Para entender a preparação da rede, [leia Preparar a rede da sua organização para o Teams.](prepare-network.md)

5.  Permitir acesso de rede ao Exchange, Ao SharePoint e ao OneDrive for Business no Microsoft 365 ou no Office 365: [URLs do Office 365 e intervalos de endereços IP.](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)

> [!NOTE]
> Locatários criados após 1º de setembro de 2019 são provisionados no modo Somente equipes.
> 
> [!IMPORTANT]
> Se você implantou o Skype for Business Server e seu locatário foi provisionado APÓS 1º de setembro de 2019, entre em contato com o suporte para habilitar os recursos de coexistência do Teams. Certifique-se de que sua "política de atualização de toda a organização" está definida como "Modo <span class="underline">ilha"</span> antes de atribuir licenças do Teams a um usuário.

## <a name="migration-starting-points"></a>Pontos de partida da migração

Sua jornada para o Microsoft 365 ou o Office 365 e os recursos disponíveis no Teams, dependendo do ponto de partida e da existência do Skype for Business ou do servidor Lync local. As seções a seguir detalham recursos básicos e opções de configuração, além dos pré-requisitos acima. Nós quebramos os cenários de ponto de partida para os seguintes tópicos:

**Configuração do Locatário do Teams:** os modos de locatário e usuário são usados para controlar o comportamento do destinatário. Essas configurações podem ser atribuídas no nível do locatário ou no nível do usuário em uma organização. Para saber mais, leia [Coexistência com o Skype for Business.](coexistence-chat-calls-presence.md)

**Chat/Comunicação externa no Teams:** os serviços de chat referem-se a conversas de chat ponto a ponto ou em grupo dentro e na organização ou externamente à organização. A comunicação externa também é chamada de federação no Skype for Business.

**Criar e exibir** reuniões no Teams: um usuário sempre pode criar reuniões online por meio do complemento Outlook Teams e o discagem PSTN está disponível em todos os cenários quando o usuário é licenciado. O Teams e o Skype for Business armazenam informações de calendário na caixa de correio do Exchange do usuário. No local, o servidor Exchange deve ser Exchange Server 2016 CU3 ou superior para que o cliente do Teams possa interagir com a caixa de correio do usuário. Sem o acesso à caixa de correio do Exchange, o ícone Calendário no Teams não será exibido e o usuário não poderá exibir, criar ou modificar reuniões no cliente do Teams.

**Recursos de chamada VoIP/PSTN** no Teams: as chamadas podem ser De voz por IP (VoIP) ou PSTN (Rede Telefônica Pública Comutado). A conectividade VoIP acontece de forma nativa entre clientes do Teams, enquanto a conectividade PSTN acontece quando um usuário disca um número de telefone externo.  

As equipes suportam dois tipos de conectividade PSTN. Plano de Chamada da Microsoft, quando a Microsoft fornece infraestrutura de telefonia, incluindo o número de telefone de um usuário, ou a configuração de Roteamento Direto, em que o cliente fornece a conectividade de telefonia por meio de um SBC (Controlador de Borda de Sessão) para o usuário do Teams.  
Para saber mais, leia [Qual Plano de Chamada é o melhor para você?](calling-plan-landing-page.md) e Roteamento Direto do Sistema de [Telefonia.](direct-routing-landing-page.md)

**Colaboração de Equipes** e Canais no Teams: No Teams, as equipes são grupos de pessoas reunidas para trabalho, projetos ou interesses comuns. As equipes são feitas de canais. Cada canal é criado em torno de um tópico, como "Eventos da Equipe", um nome de departamento ou apenas por diversão. Os canais são onde você faz reuniões, conversa e trabalha em arquivos juntos. Durante a colaboração

OneDrive for Business (compartilhamento de arquivos **P2P)** no Teams: fora do Teams e dos Canais, os usuários do Teams podem compartilhar arquivos ponto a ponto usando o OneDrive for business ou outros programas de arquivos de compartilhamento P2P, como Arquivos Citrix, DropBox, Box e Google Drive. Para o OneDrive for Business, um usuário deve ter uma licença do SharePoint Online atribuída.

**Plataforma de** Aplicativos: os aplicativos oferecem ferramentas in-loe mais precisas para sua organização tirar o melhor do Teams. Esses aplicativos combinam a funcionalidade de guias, extensões de mensagens, conectores e bots fornecidos pela Microsoft, criado por terceiros ou por desenvolvedores em sua organização.

**Recursos de Segurança e Conformidade:** O Teams tem uma ampla variedade de informações para ajudá-lo com as áreas de conformidade, incluindo políticas de retenção, Proteção contra Perda de Dados (DLP), Descoberta Online e retenção legal para canais, chats e arquivos, pesquisa de log de auditoria. Para saber mais, leia [Segurança e conformidade no Microsoft Teams.](security-compliance-overview.md)  

> [!NOTE]
> Os recursos avançados de DescobertaSuce exigem licenciamento E5.

[Compare as opções de licenciamento.](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)

Leia [como o Exchange e o Microsoft Teams interagem](exchange-teams-interact.md) para saber quais recursos de conformidade estão disponíveis em seu cenário.

## <a name="organizations-span-classunderlinewithoutspan-skype-for-business-or-lync-server"></a>Organizações **<span class="underline">sem</span>** o Skype for Business ou o Lync Server

Este ponto de partida supõe que sua organização não utilize o Skype for Business ou o Lync Server no momento e o Teams será seu primeiro aplicativo no Microsoft 365 ou no Office 365. A tabela a seguir detalha a configuração de alto nível e os recursos do usuário final do Teams para os principais serviços.

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
<td>Modo Somente equipes, todos os recursos de chat e chamada estão apenas no Teams.</td>
</tr>
<tr class="even">
<td>Chat/Comunicação Externa no Teams</td>
<td><p>Comunicação interna (interna do Microsoft 365 ou Office 365) e comunicação de chat externo possível no Teams.</p>
<p><em>Observação: as entradas DNS devem ser configuradas para acesso externo. Os registros DNS do Skype for Business são necessários mesmo que você não tenha o Skype for Business local ou no Microsoft 365 ou Office 365, para permitir a federação com ambientes do Lync e do Skype for Business:<br />
<a href="https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records">Registros do Sistema de Nomes de Domínio Externo</a></em></p></td>
</tr>
<tr class="odd">
<td>Criar e exibir Reuniões no Teams</td>
<td><p>É possível criar reuniões internas e externas por meio do add-in do Outlook.</p>
<p>O recurso discagem PSTN e discagem está disponível com as licenças de AudioConferência.</p>
<p>O acesso ao calendário do Teams requer o Exchange 2016 CU3+ local implantado com a implantação híbrida do Exchange estabelecida: crie uma implantação híbrida com o assistente <a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">de Configuração Híbrida.</a> </p>
<p>Além da configuração híbrida do Exchange, estabeleça a autenticação OAuth do Exchange: Configure a autenticação OAuth entre as organizações <a href="https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help"> do Exchange e do Exchange Online".</p>

</p></td>
</tr>
<tr class="even">
<td>Recursos de Chamada<br />
VoIP/PSTN no Teams</td>
<td><p>O VoIP interna e externamente para o locatário está disponível.</p>
<p>Os serviços PSTN podem ser configurados por meio do Microsoft Phone System, além de adicionar um Plano de Chamada da Microsoft ou Roteamento Direto.</p></td>
</tr>
<tr class="odd">
<td>Colaboração de Equipes e Canais no Teams</td>
<td><p>Para ter experiência completa, incluindo recursos de conformidade, uma licença do SharePoint Online precisa ser atribuída ao usuário.</p>
<p>A migração de sites locais existentes do SharePoint não é necessária.</p></td>
</tr>
<tr class="even">
<td>OneDrive for Business (compartilhamento de arquivos P2P)</td>
<td>O OneDrive for Business requer que um usuário tenha uma licença do SharePoint Online atribuída. Sem essa licença, o compartilhamento de arquivos ponto a ponto não será possível.</td>
</tr>
<tr class="odd">
<td>Plataforma de aplicativos</td>
<td>Os usuários poderão usar os aplicativos designados disponíveis para eles de acordo com as políticas da sua empresa.<br />
Saiba mais aqui: <a href="https://docs.microsoft.com/microsoftteams/admin-settings">Configurações de administração para aplicativos no Teams</a></td>
</tr>
<tr class="even">
<td>Recursos de Segurança e Conformidade</td>
<td><ul>
<li><p>As políticas de retenção estão disponíveis.</p></li>
<li><p>Há suporte para Descobertas EDiscovery e Espera Legal para conformidade em mensagens de canal.</p></li>
<li><p>As políticas de Prevenção contra Perda de Dados (DLP) estão disponíveis.</p></li>
</ul>
<p>Conjunto completo de recursos disponível com o Exchange Online; O Exchange local dá suporte à maioria desses recursos. Para ver uma lista completa, veja <a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">como o Exchange e o Teams interagem.</a></p></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-without-skype-for-business-or-lync-server"></a>Etapas de habilitação para organizações sem o Skype for Business ou o Lync Server

1.  Conheça pré-requisitos detalhados na seção Iniciar Aqui acima

2.  Alternar o locatário para o modo Somente equipes (somente para locatários [existentes): definindo suas configurações de coexistência e atualização.](setting-your-coexistence-and-upgrade-settings.md)

3.  Configure seu locatário de acordo com as políticas comerciais/da empresa da sua [empresa: Gerencie](enable-features-office-365.md)as configurações do Microsoft Teams para sua organização.

4.  Implantar o cliente do Teams para seus usuários: [Obter clientes para o Teams](get-clients.md)

5.  Conduzir seu programa de adoção  
    [Adotar o Microsoft Teams](adopt-microsoft-teams-landing-page.md)
    
    [Lista de verificação de início rápido da adoção do Microsoft Teams](teams-adoption-quick-start-checklist.md)

6.  Começar a planejar a movimentação de outras cargas de trabalho para o Microsoft 365 ou o Office 365

## <a name="organizations-span-classunderlinewithspan-skype-for-business-or-lync-server"></a>Organizações **<span class="underline">com</span>** o Skype for Business ou o servidor Lync

Este ponto de partida supõe que sua organização utilize o Skype for Business 2019 ou 2015+ ou o Lync 2013+ servidor local. Já temos orientações abrangentes para as organizações que migram de servidores locais para o Teams e devem ser seguidas para esses cenários. Essa orientação é específica para o cenário de que o Teams é o primeiro aplicativo que você usa no Microsoft 365 ou no Office 365. A tabela a seguir detalha a configuração de alto nível e os recursos do usuário final do Teams para os principais serviços.

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
<td>Modo ilhas.</td>
</tr>
<tr class="even">
<td>Chat/Comunicação Externa no Teams</td>
<td>Interna em seu próprio locatário apenas, a comunicação externa (federação) é por meio da implantação do servidor Skype for Business ou do Lync.</td>
</tr>
<tr class="odd">
<td>Criar e exibir Reuniões no Teams</td>
<td><p>É possível criar reuniões internas e externas por meio do add-in do Outlook.</p>
<p>O recurso discagem PSTN e discagem está disponível com as licenças de AudioConferência.</p>
<p>O acesso ao calendário do Teams requer o Exchange 2016 CU3+ local implantado com a implantação híbrida do Exchange:<br />
<a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">Crie uma implantação híbrida com o assistente de Configuração Híbrida.</a></p>
<p>O administrador pode controlar o add-in do Outlook do Skype for Business por meio do atributo PreferredMeetingProviderForIslandsMode da política de reunião do Teams:<a href="https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps"> set-csteamsmeetingpolicy.</a></p> 
</td>
</tr>
<tr class="even">
<td>Recursos de Chamada<br />
VoIP/PSTN no Teams</td>
<td><p>O VoIP interno para o locatário está disponível.</p>
<p>Os serviços PSTN ou Plano de Chamada não estarão disponíveis até que o usuário seja movido para a experiência somente do Teams.</p></td>
</tr>
<tr class="odd">
<td>Colaboração de Equipes e Canais no Teams</td>
<td><p>Para ter experiência completa, incluindo recursos de conformidade, uma licença do SharePoint Online precisa ser atribuída ao usuário.</p>
<p>A migração de sites locais existentes do SharePoint não é necessária.</p></td>
</tr>
<tr class="even">
<td>OneDrive for Business (compartilhamento de arquivos P2P)</td>
<td>O OneDrive for Business requer que um usuário tenha uma licença do SharePoint Online atribuída. Sem essa licença, o compartilhamento de arquivos ponto a ponto não será possível.</td>
</tr>
<tr class="odd">
<td>Plataforma de aplicativos</td>
<td>Os usuários poderão usar os aplicativos designados disponíveis para eles de acordo com as políticas da sua empresa.<br />
Saiba mais aqui: <a href="https://docs.microsoft.com/microsoftteams/admin-settings">Configurações de administração para aplicativos no Teams</a></td>
</tr>
<tr class="even">
<td>Recursos de Segurança e Conformidade</td>
<td><ul>
<li><p>As políticas de retenção estão disponíveis.</p></li>
<li><p>Há suporte para Descobertas EDiscovery e Espera Legal para conformidade em mensagens de canal.</p></li>
<li><p>As políticas de Prevenção contra Perda de Dados (DLP) estão disponíveis.</p></li>
</ul>
<p>Conjunto completo de recursos disponível com o Exchange Online; O Exchange local dá suporte à maioria desses recursos. Para ver uma lista completa, veja <a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">como o Exchange e o Teams interagem.</a></p>
<ul>
</ul></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-with-skype-for-business-server"></a>Etapas de habilitação para organizações com o Skype for Business Server  

1.  Conheça pré-requisitos detalhados na seção Iniciar Aqui acima.

2.  Alternar o locatário para o modo Ilhas (para locatários provisionados APÓS 01/09/2019, contate o suporte para fazer essa alteração)  
    [Definir suas configurações de coexistência e atualização](setting-your-coexistence-and-upgrade-settings.md)

3.  Configurar seu locatário de acordo com as políticas comerciais/da empresa da sua empresa  
    [Gerenciar as configurações do Microsoft Teams para sua organização](enable-features-office-365.md)

4.  Implantar o cliente do Teams  
    [Obter clientes para o Teams](get-clients.md)

5.   Conduzir seu programa de adoção  
    [Adotar o Microsoft Teams](adopt-microsoft-teams-landing-page.md)<br/>
    [Lista de verificação de início rápido da adoção do Microsoft Teams](teams-adoption-quick-start-checklist.md)

6.  Começar a planejar a movimentação de outras cargas de trabalho para o Microsoft 365 ou o Office 365

7.  Estabeleça o Skype for Business híbrido e siga os caminhos de atualização recomendados para servidores do Skype for Business e do Lync  
    [Atualizar do Skype for Business local para o Teams](upgrade-to-teams-execute-skypeforbusinesshybridonprem.md)

## <a name="closing-statement"></a>Instrução de fechamento

O Microsoft Teams pode ser um habilitador para sua organização reunir todos os funcionários, trabalhadores da informação e trabalhadores da linha de frente em uma única plataforma. Você pode [começar hoje.](https://products.office.com/microsoft-teams/group-chat-software) Você pode manter contato com todos os nossos comunicados mais recentes e atualizações mensais de produtos [aqui.](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog)

Além disso, à medida que as empresas em todo o mundo gerenciam a situação atual do COVID-19, criamos uma série de conteúdo que o ajudará a utilizar o Teams para o máximo impacto em sua organização.

  - Nosso [compromisso com os clientes durante o COVID-19](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)

  - [Duas semanas em: o que aprendemos sobre o trabalho remoto](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/18/making-the-switch-to-remote-work-5-things-weve-learned/)

  - [Fornecendo reuniões e eventos online](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/delivering-online-meetings-events/)

  - [Ajudar empresas pequenas e de médio porte a trabalhar remotamente com o Teams](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/helping-smb-customers-work-remotely-microsoft-teams/)

  - [Transformação digital de eventos ao vivo: observações de Bob Bejan a partir do frontline](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/13/digital-transformation-live-events-bob-bejans-observations-frontline/)

  - [As 9 principais maneiras que o TI da Microsoft está possibilitando o trabalho remoto para seus funcionários](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/top-9-ways-microsoft-it-enabling-remote-work-employees/)

  - [Trabalhe remotamente, mantenha a segurança — dicas para CISOs](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/work-remotely-stay-secure-ciso-tips/)

  - [Ajudar professores e alunos a mudar para o aprendizado remoto](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/11/helping-teachers-students-switch-remote-learning/)

  - [Mantenha-se produtivo enquanto trabalha remotamente com o Microsoft Teams](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/10/staying-productive-while-working-remotely-with-microsoft-teams/)

## <a name="support-services-reference"></a>Referência de Serviços de Suporte

O Teams depende do Exchange Online, do SharePoint Online, do OneDrive for Business e dos Grupos do Microsoft 365 para fornecer aos usuários uma experiência totalmente integrada do Microsoft 365 ou do Office 365. Conforme mencionado acima, o Teams funcionará sem a implantação completa desses serviços, com recursos limitados. Você pode ler mais sobre o Teams e seus pré-requisitos aqui: [Bem-vindo ao Teams.](teams-overview.md)

Para informações específicas sobre cada um dos serviços listados acima, siga os links abaixo:

  - O Exchange Online é usado para recursos de calendário e para armazenar mensagens ponto a ponto no Teams. Para saber mais, leia [como o Exchange e o Teams interagem](exchange-teams-interact.md)

> [!IMPORTANT]
> Para a interopção do Teams com o Exchange local, você deve configurar o novo protocolo de autenticação OAuth do Exchange conforme descrito em Configurar autenticação [OAuth](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)entre as organizações do Exchange e do Exchange Online.

  - O SharePoint é usado para o compartilhamento de arquivos em canais, enquanto o /OneDrive for Business é usado para compartilhamento de arquivos em um chat em grupo ou 1:1. Para saber mais, leia [como o SharePoint Online e o OneDrive for Business interagem com o Microsoft Teams.](sharepoint-onedrive-interact.md)

  - [Os Grupos do Microsoft 365](office-365-groups.md) são usados para criação/gerenciamento de equipe e canal.


## <a name="related-topics"></a>Tópicos relacionados

[Cartazes de soluções de telefonia e arquitetura de TI do Microsoft Teams](teams-architecture-solutions-posters.md#teams-as-part-of-microsoft-365)

[Planejar conectividade híbrida entre o Skype for Business Server e o Office 365](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity)

[Dar suporte a trabalhadores remotos usando o Teams](support-remote-work-with-teams.md)

[Trabalhar remotamente com o Microsoft 365](https://aka.ms/remote-work)
