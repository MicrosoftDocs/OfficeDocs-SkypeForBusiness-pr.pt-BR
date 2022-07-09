---
title: Planejar a conectividade híbrida | Skype for Business Server e Teams
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
search.appverid: MET150
description: Planeje implementar a conectividade híbrida entre o Skype for Business Server e o Teams configurando Skype for Business modo híbrido.
ms.custom: seo-marvel-jun2020
ms.openlocfilehash: a73b14a3642a216ff9cbbe919b586979aabf6a81
ms.sourcegitcommit: 15ec17eff4ad4c962d00b8683513f9b269d82917
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/09/2022
ms.locfileid: "66695044"
---
# <a name="plan-hybrid-connectivity-between-skype-for-business-server-and-teams"></a>Planejar a conectividade híbrida entre o Skype for Business Server e o Teams

> [!Important]
> Embora o Skype for Business Online tenha sido desativado desde 2021, os produtos locais Skype for Business Server 2019, Skype for Business Server 2015 e Lync Server 2013 ainda têm suporte. Além disso, a Microsoft dá suporte a ambientes híbridos entre esses produtos locais e o Microsoft Teams. Isso permite que as organizações com essas implantações locais migrem seus usuários para o TeamsOnly.  Por fim, o Cloud Connector Edition Skype for Business Server não tem mais suporte. Os clientes que exigem conectividade PSTN local devem usar o [Roteamento Direto](/MicrosoftTeams/direct-routing-landing-page).


Leia este tópico para saber como planejar a conectividade híbrida entre o Skype for Business Server ou o Lync Server 2013 e o Teams. Configurar a conectividade híbrida é a primeira etapa na mudança do ambiente local para um ambiente somente do Microsoft Teams na nuvem.

Em uma implantação local do Skype for Business Server, os usuários do Skype for Business também podem usar o Teams, mas nem todas as funcionalidades do Teams estão disponíveis para esses usuários, desde que estejam configurados para usar a implantação Skype for Business Server local. Esses usuários são ditos como "hospedados" localmente e determinadas funcionalidades do Teams não estão disponíveis enquanto esses usuários estão hospedados localmente, por exemplo:

- Chamadas federadas e chats por meio do cliente do Teams do usuário com usuários em outras organizações não estão disponíveis
- Comunicação de interoperabilidade por meio do cliente do Teams do usuário com outros usuários na organização que usam Skype for Business cliente.
- Funcionalidade de chamada PSTN (se o usuário receber uma licença do Sistema de Telefonia).

Para obter a funcionalidade completa do Teams, esses usuários devem ser movidos do Skype for Business local para a nuvem, momento em que o usuário se torna TeamsOnly. O ato de mover um usuário do local para a nuvem definirá o modo de coexistência do usuário como TeamsOnly. Depois que os usuários são movidos para a nuvem e o TeamsOnly, todos os chats e chamadas de entrada chegam ao cliente do Teams (ao contrário do uso lado a lado do Teams).  Para obter mais informações, consulte [a coexistência do Teams](/microsoftteams/coexistence-chat-calls-presence) com Skype for Business e as diretrizes de migração e interoperabilidade para organizações que usam o [Teams junto com o Skype for Business](/microsoftteams/migration-interop-guidance-for-teams-with-skype).

Mover usuários entre o local e o TeamsOnly na nuvem requer a configuração Skype for Business modo híbrido. Além disso, antes de encerrar sua implantação local Skype for Business mover todos os usuários do local para a nuvem.   Com a conectividade híbrida configurada, é possível optar por migrar os usuários para a nuvem com base na sua agenda e na necessidade de negócios.  Com o Roteamento Direto, você pode aproveitar sua infraestrutura de voz local enquanto migra para a nuvem e após a conclusão da migração.

Este tópico descreve os requisitos de infraestrutura e sistema que você precisará para configurar a conectividade híbrida entre sua implantação local Skype for Business Server existente e o Teams.

Depois de ler este tópico e estiver pronto para configurar a conectividade híbrida, consulte Configurar a conectividade híbrida entre o [Skype for Business Server e o Teams](configure-hybrid-connectivity.md). Os tópicos de configuração fornecem diretrizes passo a passo para configurar a conectividade híbrida entre sua implantação local e o Teams.


## <a name="implications-of-the-retirement-of-skype-for-business-online"></a>Implicações da desativação do Skype for Business Online
É importante lembrar que, antes e depois da desativação do Skype for Business Online, os usuários hospedados no Skype for Business Server local podem usar o Teams, mas não podem ser TeamsOnly. (Os usuários locais estão no modo Ilhas por padrão e recebem qualquer modo diferente do TeamsOnly). Os usuários só podem experimentar os benefícios completos do Teams, em particular federação, suporte PSTN e garantia de que todos os chats de entrada e chamadas chegarão no Teams, quando estiverem no modo TeamsOnly. 

A desativação do Skype for Business Online não tem impacto sobre o ciclo de vida de suporte existente do Skype for Business Server ou do Lync Server 2013.  No entanto, a desativação do Skype for Business Online afeta determinados aspectos de como  os usuários fazem a transição para a nuvem e se tornam *TeamsOnly* em organizações com o Skype for Business Server local ou o Lync Server 2013, incluindo organizações híbridas existentes. O uso do híbrido como uma configuração de pré-requisito para fazer a transição do local para a nuvem (por exemplo, TeamsOnly) permanece inalterado.

Antes da desativação do Skype for Business Online, as organizações híbridas poderiam consistir em três tipos básicos de usuários: 
- Usuários locais (que podem ou não usar o Teams, mas não no modo Somente teams) 
- Usuários online com qualquer modo de coexistência diferente do TeamsOnly
- Usuários do TeamsOnly.

Após a desativação do Skype for Business Online, no entanto, as organizações híbridas só podem consistir em dois tipos básicos de usuários: 
- Usuários locais (que podem ou não usar o Teams, mas não no modo TeamsOnly)
- Somente usuários do Teams. 

Para que as organizações mudem do Skype for Business Server ou do Lync Server 2013 para o Teams, elas ainda devem configurar e configurar o híbrido usando o mesmo conjunto de *ferramentas, exatamente* como antes da desativação. Ao mover um usuário do local para o TeamsOnly, `-MoveToTeams` não é mais necessário especificar a opção em `Move-CsUser`. Anteriormente, se essa opção não fosse especificada, os usuários iam de ser hospedados no Skype for Business Server local para o Skype for Business Online e seu modo permanece inalterado. No entanto, como o Skype Business Online foi desativado, mover um usuário do local para a nuvem atribuirá automaticamente o modo TeamsOnly e iniciará a `Move-CsUser` conversão de suas reuniões do local para reuniões do Teams,  `-MoveToTeams` independentemente de a opção ser especificada. Isso também significa que as organizações com o Lync Server 2013, `MoveToTeams` que nunca tiveram a opção, podem mover usuários diretos para o TeamsOnly do local. 

Da mesma forma, se um novo usuário for criado diretamente no Microsoft 365 em vez do local, esse usuário terá automaticamente o modo Somente Teams, independentemente do modo do locatário. Tenha em mente que, em uma organização híbrida com pelo menos um usuário local, novos usuários devem ser criados no Active Directory local (e sincronizados com o Microsoft 365), em vez de criar diretamente um usuário no Microsoft 365, para garantir que os usuários locais possam rotear para o novo usuário, mesmo que você pretenda que o novo usuário seja um usuário de nuvem *.* Depois de criados no diretório local, esses novos usuários devem ser habilitados por sip na implantação do Skype for Business local e, se desejado, *movidos* para a nuvem para se tornarem TeamsOnly. 

Os modos de coexistência continuam a existir após a desativação do Skype for Business Online. Como antes, os usuários com contas Skype for Business Server local podem receber qualquer modo de coexistência, exceto TeamsOnly. No entanto, após a desativação, os usuários hospedados online só podem ser TeamsOnly. Não é mais possível atribuir um modo diferente do TeamsOnly a um usuário hospedado online.


> [!Important]
> As organizações híbridas existentes com usuários hospedados no Skype for Business Online que NÃO são o TeamsOnly devem se concentrar na atualização desses usuários para o modo Somente teams assim que possível. Se sua organização ainda tiver usuários hospedados no Skype for Business *Online* que não são TeamsOnly, você será agendado para uma atualização assistida pela Microsoft para fazer a transição desses usuários para o TeamsOnly. **As atualizações assistidas da Microsoft não afetarão os usuários que estão hospedados Skype for Business Server locais.** As notificações de agendamento serão enviadas com antecedência para clientes híbridos com usuários hospedados no Skype for Business Online antes que esses usuários online e não TeamsOnly sejam atualizados para o Teams.

## <a name="about-shared-sip-address-space-functionality"></a>Sobre a funcionalidade espaço de endereço SIP compartilhado

<a name="BKMK_Overview"> </a>

Com a conectividade híbrida configurada entre uma implantação local do Skype for Business Server e do Teams, você pode ter alguns usuários hospedados no local e alguns usuários hospedados online.

Esse tipo de configuração depende da funcionalidade de espaço de endereço SIP compartilhado e, às vezes, é chamado de "domínio dividido", o que significa que os usuários de um domínio, como o contoso.com, são divididos entre o uso do Skype for Business Server local e do Teams, conforme mostrado no diagrama a seguir:

![Skype for Business Híbrido conectividade – domínio dividido.](../../sfbserver2019/media/plan-hybrid-connectivity-2019-1.png)

Quando o espaço de endereço SIP compartilhado estiver configurado:

- O Azure Active Directory Connect é usado para sincronizar seu diretório local com o Microsoft 365.
- Os usuários hospedados localmente interagem com servidores Skype for Business locais.
- Os usuários hospedados online interagem com o Teams.
- Os usuários de ambos os ambientes podem se comunicar entre si.
- O Active Directory local é autoritativo. Todos os usuários devem ser criados no Active Directory local primeiro e, em seguida, sincronizados com Azure AD. Mesmo que você pretenda que o usuário esteja hospedado online, primeiro você deve criar o usuário no ambiente local e, em seguida, mover o usuário para online para garantir que o usuário seja detectável por usuários locais.

Antes que um usuário possa ser movido online, o usuário deve receber uma licença do Teams, bem como Skype for Business Online (Plano 2). **A atribuição da Skype for Business Online é necessária mesmo após a desativação do Skype for Business Online.** Se os usuários quiserem aproveitar os recursos online adicionais, como Audioconferência ou Sistema de Telefonia, você precisará atribuir a eles a licença apropriada no Microsoft 365.

## <a name="hybrid-connectivity-infrastructure-requirements"></a>Requisitos de infraestrutura de conectividade híbrida

<a name="BKMK_Infrastructure"> </a>

Para implementar a conectividade híbrida entre seu ambiente local e os serviços de comunicação do Microsoft 365, você precisa atender aos seguintes requisitos de infraestrutura:

- Uma única implantação local do Skype for Business Server ou do Lync Server implantado em uma topologia com suporte. Consulte [os requisitos de topologia](plan-hybrid-connectivity.md#BKMK_Topology) neste tópico.

- Uma organização do Microsoft 365 com o Teams.
    > [!NOTE]
    > Você pode usar apenas um único locatário para uma configuração híbrida com sua implantação local.
    
- Azure Active Directory Connect para sincronizar seu diretório local com o Microsoft 365. Para obter mais informações, [consulte Azure AD Connect: contas e permissões](/azure/active-directory/connect/active-directory-aadconnect-accounts-permissions).

- Skype for Business Server ferramentas administrativas. Eles são necessários para mover os usuários do local para a nuvem. Essas ferramentas devem ser instaladas em um servidor com acesso à implantação local e à Internet.
- Ferramentas administrativas online. Você pode usar o centro de administração do Teams ou Windows PowerShell gerenciar o Teams. Para usar o PowerShell para gerenciar o Teams, baixe e instale o Módulo do PowerShell do Teams. (O Skype for Business Online foi desativado).
- O espaço de endereço SIP compartilhado deve ser habilitado e sua implantação local deve ser configurada para usar o Microsoft 365 como um provedor de hospedagem. Para obter mais informações sobre as etapas necessárias para configurar a conectividade híbrida, consulte [Configurar conectividade híbrida](configure-hybrid-connectivity.md).

Depois de configurar a conectividade híbrida, você pode mover os usuários para o Teams. Para obter mais informações, [consulte Mover usuários do local para o Teams](move-users-from-on-premises-to-teams.md).

## <a name="server-version-requirements"></a>Requisitos de versão do servidor

<a name="BKMK_Topology"> </a>

Para configurar sua implantação para híbrido com o **Teams**, você precisa ter uma das seguintes topologias com suporte:

- Uma implantação do Skype for Business 2019 com todos os servidores executando o Skype for Business 2019.
- Uma implantação do Skype for Business 2015 com todos os servidores executando o Skype for Business 2015.
- Uma implantação do Lync Server 2013 com todos os servidores executando o Lync Server 2013.  No entanto, se a conectividade de voz híbrida for necessária, você deverá usar uma topologia de versão mista, conforme mostrado abaixo.
- Uma implantação com no máximo duas versões de servidor diferentes, conforme listado abaixo:
  - Skype for Business Server 2015 e Skype for Business Server 2019
  - Lync Server 2013 e Skype for Business Server 2019
  - Lync Server 2013 e Skype for Business Server 2015
- A partir de 31 de julho de 2022, para mover usuários entre uma implantação local e a nuvem, você deve usar as seguintes versões mínimas do Skype for Business Server ou do Lync Server:
</br>

|Produto local|Versão mínima necessária|Build mínimo necessário|
|---|---|---|
|Skype for Business Server 2019| CU6 |7.0.2046.385|
|Skype for Business Server 2015| CU12|6.0.9319.619|
|Lync Server 2013| CU10 com Hotfix 7|5.0.8308.1182|

</br>

> [!NOTE] 
> Não há suporte para o Lync Server 2010 com o Teams.


## <a name="multi-forest-support"></a>Suporte a várias florestas

<a name="BKMK_MultiForest"> </a>

A Microsoft dá suporte aos seguintes tipos de cenários híbridos de várias florestas:

- **Topologia da floresta de recursos** Nesse tipo de topologia, há uma floresta que hospeda Skype for Business Server (a floresta de recursos) e há uma ou mais florestas adicionais que hospedam identidades de conta, que acessam o Skype for Business Server na floresta de recursos. Em geral, os usuários poderão acessar a funcionalidade do Skype for Business em outra floresta se os seguintes requisitos forem atendidos:
  - Os usuários são sincronizados corretamente na floresta que hospeda o Skype for Business. Em configurações híbridas, isso significa que os usuários devem ser sincronizados como objetos de usuário desabilitados.
  - A floresta que hospeda o Skype for Business deve confiar na floresta que contém os usuários.
    Para obter detalhes sobre cenários híbridos de floresta de recursos, consulte [Implantar uma topologia de floresta de recursos para Skype for Business](configure-a-multi-forest-environment-for-hybrid.md).

- **Várias implantações do Skype for Business Server em várias florestas.** Essa configuração pode surgir como resultado de cenários de fusão e aquisição, bem como em empresas mais complexas. A consolidação de todos os usuários do local para a nuvem em uma única organização do Microsoft 365 pode ser obtida para qualquer organização com várias implantações do Skype for Business, desde que os seguintes requisitos principais sejam atendidos:
  - Deve haver no máximo uma organização do Microsoft 365 envolvida. Não há suporte para a consolidação em cenários com mais de uma organização.
  - A qualquer momento, apenas uma floresta local do Skype for Business pode estar no modo híbrido (espaço de endereço SIP compartilhado). Todas as outras florestas Skype for Business locais devem permanecer totalmente locais (e provavelmente federadas umas com as outras). Observe que essas outras organizações locais podem sincronizar com o AAD, se desejar, com novas funcionalidades para desabilitar [domínios SIP online](/powershell/module/skype/disable-csonlinesipdomain) disponíveis a partir de dezembro de 2018.

    Os clientes com implantações de Skype for Business em várias florestas devem migrar totalmente cada floresta Skype for Business individualmente para a organização do Microsoft 365 usando a funcionalidade de domínio dividido (Espaço de Endereço SIP Compartilhado). Depois que a migração de floresta for concluída, os clientes deverão desabilitar o híbrido com a implantação local antes de migrar a próxima implantação local Skype for Business implantação. Além disso, antes de serem migrados para a nuvem, os usuários locais permanecem em um estado federado com todos os usuários que não são representados no diretório local do mesmo usuário. Para obter mais detalhes, consulte [Consolidação de nuvem para Teams e Skype for Business](cloud-consolidation.md).

## <a name="federation-requirements"></a>Requisitos de federação

<a name="BKMK_Federation"> </a>

Ao configurar Skype for Business modo híbrido, você deve garantir que seus ambientes locais e online possam federar entre si.  O ambiente online tem federação aberta por padrão; o ambiente local geralmente fechou a federação por padrão.  

Os seguintes requisitos devem ser atendidos para configurar com êxito uma implantação híbrida:

- A correspondência de domínio deve ser configurada da mesma forma para sua implantação local e sua organização do Microsoft 365. Se a descoberta de parceiros estiver habilitada na implantação local, a federação aberta deverá ser configurada para sua organização online. Se a descoberta de parceiros não estiver habilitada, a federação fechada deverá ser configurada para sua organização online.
- A lista de domínios bloqueados na implantação local deve corresponder exatamente à lista de domínios bloqueados para seu locatário online.
- A lista de domínios permitidos na implantação local deve corresponder exatamente à lista de domínios permitidos para seu locatário online.
- A federação deve ser habilitada para as comunicações externas para o locatário online.

## <a name="network-considerations"></a>Considerações de rede

As seções a seguir descrevem considerações para:

- Configurações de DNS
- Considerações sobre firewall

### <a name="dns-settings-for-hybrid-deployments"></a>Configurações de DNS para implantações híbridas

<a name="BKMK_DNS"> </a>

Ao criar registros DNS para implantações híbridas, todos os registros DNS externos do Skype for Business devem apontar para a infraestrutura local. Para obter detalhes sobre os registros DNS necessários, consulte os requisitos [de DNS para Skype for Business Server](../../sfbserver/plan-your-deployment/network-requirements/dns.md).

Além disso, você precisa garantir que a resolução de DNS descrita na tabela a seguir funcione em sua implantação local. (Se você já configurou a federação no local, provavelmente já os tem.)

|Registro DNS  <br/> |Resolvível por  <br/> |Requisito de DNS  <br/> |
|:-----|:-----|:-----|
|Registro SRV dns para _sipfederationtls._tcp.\<sipdomain.com\> para todos os domínios SIP com suporte que resolvem ip(s) externos do Access Edge  <br/> |Servidor(es) de borda  <br/> |Habilite a comunicação federada em uma configuração híbrida. O Servidor de Borda precisa saber para onde rotear o tráfego federado para o domínio SIP que é dividido entre o local e o online.  <br/> Deve usar a correspondência estrita de nome DNS entre o domínio no nome de usuário e o registro SRV.  <br/> |
|Registros DNS A para FQDN do Serviço de Webconferência de Borda, por exemplo, webcon.contoso.com resolver para IP externos da Borda de WebConferência  <br/> |Computadores de usuários conectados à rede corporativa interna  <br/> |Permita que usuários online apresentem ou visualizem conteúdo em reuniões hospedadas no local. O conteúdo inclui arquivos do PowerPoint, quadros de comunicações, votações e anotações compartilhadas.  <br/> |

Dependendo de como o DNS está configurado em sua organização, pode ser necessário adicionar esses registros à zona DNS hospedada interna para os domínios SIP correspondentes para fornecer resolução DNS interna a esses registros.

### <a name="firewall-considerations-for-hybrid-deployments"></a>Considerações sobre firewall para implantações híbridas

<a name="BKMK_Firewall"> </a>

Os computadores em sua rede devem ser capazes de realizar pesquisas padrão de DNS da Internet. Se estes computadores podem atingir sites da Internet padrões, sua rede cumpre este requisito.

Dependendo da localização do data center do Microsoft Online Services, você também deve configurar seus dispositivos de firewall de rede para aceitar conexões com base em nomes de domínio curinga (por exemplo, \*todo o tráfego de .outlook.com). Se os firewalls de sua organização não oferecerem suporte a configurações de nome de caractere curinga, você terá que determinar manualmente os intervalos de endereços IP que deseja permitir e as portas especificadas.

Para obter mais informações, incluindo detalhes sobre portas e requisitos de protocolo, consulte [URLs do Microsoft 365 e intervalos de endereços IP](/microsoft-365/enterprise/urls-and-ip-address-ranges).
