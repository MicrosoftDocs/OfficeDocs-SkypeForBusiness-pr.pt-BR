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
description: Planeje implementar a conectividade híbrida entre Skype for Business Server e Teams configurando Skype for Business modo híbrido.
ms.custom: seo-marvel-jun2020
ms.openlocfilehash: ac2243613b4d3929f3d78facd4a45a4d70acda2b
ms.sourcegitcommit: 11a803d569a57410e7e648f53b28df80a53337b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/10/2021
ms.locfileid: "60887199"
---
# <a name="plan-hybrid-connectivity-between-skype-for-business-server-and-teams"></a>Planejar conectividade híbrida entre Skype for Business Server e Teams

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Leia este tópico para saber como planejar a conectividade híbrida entre Skype for Business Server e Teams. Configurar a conectividade híbrida é o primeiro passo para migrar seu ambiente local para a nuvem.

Se você tem usuários do Skype for Business local que também estão usando o Teams (lado a lado), esses usuários não têm a capacidade de interoperar com os usuários do Skype for Business a partir do cliente do Teams, nem se comunicar com os usuários em organizações federadas a partir do cliente do Teams. Para obter essa funcionalidade no Teams, esses usuários devem ser movidos do Skype for Business local para a nuvem, o que requer a configuração do modo híbrido do Skype for Business. Além disso, para a melhor experiência, esses usuários devem estar no modo Somente Teams, o que garante todas as chamadas de entrada e chats de qualquer usuário que chegar no cliente Teams usuário.

Também é necessário configurar a conectividade híbrida e mover todos os usuários para a nuvem antes de você encerrar sua implantação do Skype for Business local.  Com a conectividade híbrida configurada, é possível optar por migrar os usuários para a nuvem com base na sua agenda e na necessidade de negócios. Com o Roteamento Direto, você pode aproveitar sua infraestrutura de voz local enquanto migra para a nuvem e após a conclusão da migração.

Este tópico descreve os requisitos de infraestrutura e sistema que você precisará configurar a conectividade híbrida entre sua implantação Skype for Business Server local e Teams.

Depois de ler este tópico e estiver pronto para configurar a conectividade híbrida, consulte [Configure hybrid connectivity between Skype for Business Server and Teams](configure-hybrid-connectivity.md). Os tópicos de configuração fornecem orientações passo a passo para configurar a conectividade híbrida entre sua implantação local e Teams.

> [!Important]
> Skype for Business Online foi retirado em 31 de julho de 2021 e não está mais disponível. Além disso, a conectividade PSTN entre seu ambiente local, seja por meio do Skype for Business Server ou do Cloud Connector Edition e Skype for Business Online, não tem mais suporte.  Saiba como conectar sua rede de telefonia local a Teams usando [Roteamento Direto.](/MicrosoftTeams/direct-routing-landing-page)

## <a name="implications-of-the-retirement-of-skype-for-business-online"></a>Implicações da aposentadoria do Skype for Business Online
É importante lembrar que, antes e após a aposentadoria do Skype for Business Online, os usuários que estão no Skype for Business Server local podem usar o Teams, mas não podem ser o TeamsOnly. (Por padrão, os usuários estão no modo Ilhas). Os usuários só podem experimentar os benefícios completos da Teams, em particular o suporte a federação e PSTN, uma vez que estão no modo TeamsOnly. 

A aposentadoria do Skype for Business Online não afeta o ciclo de vida de suporte existente do Skype for Business Server ou do Lync Server 2013.  No entanto, a aposentadoria do Skype for Business Online impactou determinados aspectos de como os clientes com o Skype for Business Server local ou o Lync Server 2013, incluindo organizações híbridas existentes, transitam para a nuvem. O que não mudou desde a aposentadoria é que o uso do híbrido como o meio de transição do local para a nuvem permanece inalterado.

Antes da reforma do Skype for Business Online, as organizações híbridas poderiam consistir em três tipos básicos de usuários: 
- Usuários locais (que podem ou não usar Teams, mas não no Teams somente) 
- Usuários online com qualquer modo de coexistência diferente do TeamsOnly
- Usuários do TeamsOnly.

No entanto, após a Skype for Business online, as organizações híbridas só podem consistir em dois tipos básicos de usuários: 
- Usuários locais (Who podem ou não usar Teams, mas não no modo TeamsOnly)
- Teams Somente usuários. 

Para que as organizações mudem do Skype for Business Server ou do Lync Server 2013 para o Teams, elas ainda devem configurar e configurar o híbrido usando o mesmo conjunto de *ferramentas,* exatamente como antes da reforma . O que mudou é que, ao mover um usuário do local para o Teams, não é mais necessário especificar a opção para mover os usuários diretamente do local para o `-MoveToTeams` `Move-CsUser` TeamsOnly. Anteriormente, se essa opção não foi especificada, os usuários mudaram de Skype for Business Server local para o Skype for Business Online, e seu modo permaneceu inalterado. Como resultado da aposentadoria, ao mover um usuário do local para a nuvem com , os usuários agora são atribuídos automaticamente ao modo TeamsOnly e suas reuniões do local são automaticamente convertidas em reuniões de Teams, como se a opção tivesse sido especificada, independentemente de a opção ser `Move-CsUser` `-MoveToTeams` realmente especificada. (Isso inclui migrações do Lync Server 2013, que nunca tiveram a `MoveToTeams` opção.) 

Da mesma forma, se um novo usuário for criado diretamente no Microsoft 365 em vez de no local, esse usuário terá automaticamente Teams modo Somente independentemente do modo do locatário. Lembre-se de que, em uma organização híbrida, novos usuários devem ser criados no Active Directory local (e sincronizados no Microsoft 365), em vez de criar diretamente um usuário no Microsoft 365, para garantir que os usuários locais possam roteá-lo para o novo usuário.

Os modos de co-existência continuam a existir após a aposentadoria do Skype for Business Online. Como antes, os usuários com contas Skype for Business Server local podem ser atribuídos a qualquer modo de coexistência, exceto o TeamsOnly. No entanto, após a aposentadoria, os usuários em casa online só podem ser o TeamsOnly (em contraste com o presente em que os usuários Skype for Business Online podem ser qualquer modo).  

> [!Important]
> - As organizações híbridas existentes com usuários Skype for Business Online que não são o TeamsOnly devem se concentrar na atualização desses usuários para Teams modo Somente assim que possível. Se sua organização ainda tiver usuários no Skype for Business Online que não são o TeamsOnly, você pode estar agendado para uma atualização assistida pela Microsoft para fazer a transição desses usuários para o TeamsOnly. Isso não afetará os usuários que estão Skype for Business Server local. As notificações de agendamento serão enviadas com antecedência para clientes híbridos com usuários Skype for Business online antes que esses usuários online, que não sejam do TeamsOnly, sejam atualizados para Teams.
> - Não é mais possível atribuir um modo diferente do TeamsOnly a um usuário que está em casa online.

## <a name="about-shared-sip-address-space-functionality"></a>Sobre a funcionalidade espaço de endereço SIP compartilhado

<a name="BKMK_Overview"> </a>

 Com a conectividade híbrida configurada entre uma implantação local do Skype for Business Server e Teams, você pode ter alguns usuários no local e alguns usuários online.

Esse tipo de configuração se baseia na funcionalidade de espaço de endereço SIP compartilhado e, às vezes, é chamado de "domínio dividido"-- o que significa que os usuários de um domínio, como o contoso.com, são divididos entre o uso do Skype for Business Server local e o Teams, conforme mostrado no diagrama a seguir:

![Skype for Business Híbrido conectividade - domínio dividido.](../../sfbserver2019/media/plan-hybrid-connectivity-2019-1.png)

Quando o espaço de endereço SIP compartilhado é configurado:

- Azure Active Directory Conexão é usado para sincronizar seu diretório local com Microsoft 365.
- Os usuários que estão no local interagem com servidores Skype for Business locais.
- Os usuários que estão online podem interagir com o Teams e, até 31 de julho de 2021, Skype for Business Online com base em seu modo de co-existência.
- Os usuários de ambos os ambientes podem se comunicar uns com os outros.
- O Active Directory local é autoritativo. Todos os usuários devem ser criados no Active Directory local primeiro e sincronizados com o Azure AD. Mesmo que você pretenda que o usuário seja criado online, você deve primeiro criar o usuário no ambiente local e, em seguida, mover o usuário para online para garantir que o usuário seja descoberto pelos usuários locais.

Para que um usuário possa ser movido online, o usuário deve ter uma licença Teams, bem como Skype for Business Online (Plano 2). **A atribuição da licença Skype for Business Online é necessária mesmo após a aposentadoria do Skype for Business Online.** Se os usuários quiserem aproveitar recursos online adicionais, como Audioconferência ou Sistema de Telefonia, você precisará atribuir a eles a licença apropriada Microsoft 365.

## <a name="hybrid-connectivity-infrastructure-requirements"></a>Requisitos de infraestrutura de conectividade híbrida

<a name="BKMK_Infrastructure"> </a>

Para implementar a conectividade híbrida entre seu ambiente local e Microsoft 365 serviços de comunicação, você precisa atender aos seguintes requisitos de infraestrutura:

- Uma única implantação local do Skype for Business Server ou do Lync Server implantado em uma topologia com suporte. Consulte [Requisitos de topologia](plan-hybrid-connectivity.md#BKMK_Topology) neste tópico.

- Uma Microsoft 365 com Teams.
    > [!NOTE]
    > Você pode usar apenas um único locatário para uma configuração híbrida com sua implantação local.
    
- Azure Active Directory Conexão sincronizar seu diretório local com Microsoft 365. Para obter mais informações, consulte [Azure AD Conexão: Contas e permissões.](/azure/active-directory/connect/active-directory-aadconnect-accounts-permissions)

- Skype for Business Server ferramentas administrativas. Eles são necessários para mover os usuários do local para a nuvem. Essas ferramentas devem ser instaladas em um servidor com acesso à implantação local e à Internet.
- Ferramentas administrativas online. Você pode usar o centro de administração Teams ou Windows PowerShell gerenciar Teams. Para usar o PowerShell para gerenciar Teams, baixe e instale o módulo Teams PowerShell. (O Skype for Business Conector Online foi retirado).
- O espaço de endereço SIP compartilhado deve ser habilitado e sua implantação local deve ser configurada para usar Microsoft 365 como provedor de hospedagem. Para obter mais informações sobre as etapas necessárias para configurar a conectividade híbrida, consulte [Configure hybrid connectivity](configure-hybrid-connectivity.md).

Depois de configurar a conectividade híbrida, você pode mover os usuários para Teams. Para obter mais informações, consulte [Move users from on-premises to Teams](move-users-from-on-premises-to-teams.md).

## <a name="server-version-requirements"></a>Requisitos de versão do servidor

<a name="BKMK_Topology"> </a>

Para configurar sua implantação híbrida **com Teams**, você precisa ter uma das seguintes topologias com suporte:

- Uma implantação do Skype for Business 2019 com todos os servidores executando o Skype for Business 2019.
- Uma implantação do Skype for Business 2015 com todos os servidores executando o Skype for Business 2015.
- Uma implantação do Lync Server 2013 com todos os servidores executando o Lync Server 2013.  No entanto, se a conectividade de voz híbrida for necessária, você deverá usar uma topologia de versão misturada, conforme abaixo.
- Uma implantação com no máximo 2 versões de servidor diferentes conforme listado abaixo:
  - Skype for Business Server 2015 e Skype for Business Server 2019
  - Lync Server 2013 e Skype for Business Server 2019
  - Lync Server 2013 e Skype for Business Server 2015

Se a voz híbrida for desejada em qualquer *topologia*, tanto o servidor de borda designado como a Borda de Federação quanto o pool associado à federação SIP devem estar executando Skype for Business 2015 ou posterior. Os usuários podem permanecer em um Pool do Lync 2013 se houver um. Para obter mais detalhes, consulte [Plan your voice solution](/MicrosoftTeams/cloud-voice-landing-page).

> [!NOTE]
> O Lync Server 2010 não tem suporte com Teams.

## <a name="multi-forest-support"></a>Suporte a várias florestas

<a name="BKMK_MultiForest"> </a>

A Microsoft dá suporte aos seguintes tipos de cenários híbridos de várias florestas:

- **Topologia de floresta de recursos.** Nesse tipo de topologia, há uma floresta que hospeda Skype for Business Server (a floresta de recursos) e há uma ou mais florestas adicionais que hospedam identidades de conta, que acessam o Skype for Business Server na floresta de recursos. Em geral, os usuários podem acessar Skype for Business funcionalidade em outra floresta se os seguintes requisitos são atendidos:
  - Os usuários são sincronizados corretamente na floresta que hospeda Skype for Business. Em configurações híbridas, isso significa que os usuários devem ser sincronizados como objetos de usuário desabilitados.
  - A hospedagem Skype for Business floresta deve confiar na floresta que contém os usuários.
    Para obter detalhes sobre cenários híbridos de floresta de recursos, consulte [Deploy a resource forest topology for hybrid Skype for Business](configure-a-multi-forest-environment-for-hybrid.md).

- **Várias implantações de Skype for Business Server em várias florestas.** Essa configuração pode surgir como resultado de cenários de fusão e aquisição, bem como em empresas mais complexas. A consolidação de todos os usuários do local para a nuvem em uma única organização Microsoft 365 pode ser alcançada para qualquer organização com várias implantações Skype for Business, desde que os seguintes requisitos principais sejam atendidos:
  - Deve haver no máximo uma organização Microsoft 365 envolvida. Não há suporte para consolidação em cenários com mais de uma organização.
  - A qualquer momento, apenas uma floresta Skype for Business local pode estar no modo híbrido (espaço de endereço SIP compartilhado). Todas as outras florestas Skype for Business locais devem permanecer totalmente no local (e provavelmente federadas umas com as outras). Observe que essas outras organizações locais podem sincronizar com AAD se desejar com a nova funcionalidade para desabilitar os [domínios SIP](/powershell/module/skype/disable-csonlinesipdomain) online disponíveis a partir de dezembro de 2018.

    Os clientes com implantações de Skype for Business em várias florestas devem migrar totalmente cada floresta Skype for Business individualmente para a organização Microsoft 365 usando a funcionalidade de domínio dividido (Espaço de Endereço SIP Compartilhado). Depois que a migração de floresta for concluída, os clientes devem desabilitar o híbrido com a implantação local antes de migrar a próxima implantação local Skype for Business implantação. Além disso, antes de serem migrados para a nuvem, os usuários locais permanecem em um estado federado com todos os usuários que não são representados no diretório local do mesmo usuário. Para obter mais detalhes, consulte [Consolidação de nuvem para Teams e Skype for Business](cloud-consolidation.md).

## <a name="federation-requirements"></a>Requisitos de federação

<a name="BKMK_Federation"> </a>

Ao configurar Skype for Business modo híbrido, você deve garantir que seus ambientes locais e online possam se federar uns com os outros.  O ambiente online tem federação aberta por padrão; o ambiente local geralmente fechou a federação por padrão.  

Os seguintes requisitos devem ser atendidos para configurar com êxito uma implantação híbrida:

- A correspondência de domínio deve ser configurada da mesma forma para sua implantação local e sua Microsoft 365 organização. Se a descoberta do parceiro estiver habilitada na implantação local, a federação aberta deverá ser configurada para sua organização online. Se a descoberta do parceiro não estiver habilitada, a federação fechada deverá ser configurada para sua organização online.
- A lista de domínios bloqueados na implantação local deve corresponder exatamente à lista De domínios bloqueados para seu locatário online.
- A lista Domínios Permitidos na implantação local deve corresponder exatamente à lista Domínios Permitidos para seu locatário online.
- A federação deve estar habilitada para as comunicações externas para o locatário online.

## <a name="network-considerations"></a>Considerações de rede

As seções a seguir descrevem considerações para:

- Configurações dns
- Considerações sobre firewall

### <a name="dns-settings-for-hybrid-deployments"></a>Configurações dns para implantações híbridas

<a name="BKMK_DNS"> </a>

Ao criar registros DNS para implantações híbridas, todos os Skype for Business DNS externos devem apontar para a infraestrutura local. Para obter detalhes sobre registros DNS necessários, consulte os requisitos [dns para Skype for Business Server](../../sfbserver/plan-your-deployment/network-requirements/dns.md).

Além disso, você precisa garantir que a resolução DNS descrita na tabela a seguir funcione em sua implantação local. (Se você já configurou a federação para o local, provavelmente já tem isso.)

|Registro DNS  <br/> |Resolvêvel por  <br/> |Requisito de DNS  <br/> |
|:-----|:-----|:-----|
|Registro SRV DNS para _sipfederationtls._tcp.\<sipdomain.com\> para todos os domínios SIP com suporte que resolvem ip(s) externos de Borda de Acesso  <br/> |Servidor(s) de borda  <br/> |Habilitar a comunicação federada em uma configuração híbrida. O Servidor de Borda precisa saber para onde encaminhar o tráfego federado para o domínio SIP dividido entre local e online.  <br/> Deve usar a correspondência estrita de nome DNS entre o domínio no nome do usuário e o registro SRV.  <br/> |
|Registros DNS A para FQDN do Serviço de WebConferência de Borda, por exemplo, webcon.contoso.com resolução para IP externos de Borda de WebConferência  <br/> |Computadores de usuários conectados à rede corporativa interna  <br/> |Permitir que os usuários online apresentem ou exibirem conteúdo em reuniões hospedadas no local. O conteúdo inclui PowerPoint, whiteboards, votações e anotações compartilhadas.  <br/> |

Dependendo de como o DNS é configurado em sua organização, talvez seja necessário adicionar esses registros à zona DNS hospedada interna para que os domínios SIP correspondentes forneçam resolução DNS interna a esses registros.

### <a name="firewall-considerations-for-hybrid-deployments"></a>Considerações sobre firewall para implantações híbridas

<a name="BKMK_Firewall"> </a>

Os computadores em sua rede devem ser capazes de executar as consultas DNS padrão da Internet. Se estes computadores podem atingir sites da Internet padrões, sua rede cumpre este requisito.

Dependendo do local do seu data center Microsoft Online Services, você também deve configurar seus dispositivos de firewall de rede para aceitar conexões com base em nomes de domínio curinga (por exemplo, todo o tráfego de \* .outlook.com). Se os firewalls da sua organização não suportam configurações de nome curinga, você terá que determinar manualmente os intervalos de endereço IP que você gostaria de permitir e as portas especificadas.

Para obter mais informações, incluindo detalhes sobre portas e requisitos de protocolo, [consulte Microsoft 365 URLs e intervalos de endereços IP.](/microsoft-365/enterprise/urls-and-ip-address-ranges)
