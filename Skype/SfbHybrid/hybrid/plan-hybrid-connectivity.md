---
title: Planejar conexão híbrida | Integração do Office 365 do Skype for Business Server 2019
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Considerações de planejamento para implementar a conectividade híbrida entre o Skype for Business Server e o Skype for Business online ou o Teams.
ms.openlocfilehash: 1a1513b307c6f55f6b403a0d5db85ac14d1f7a6f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043373"
---
# <a name="plan-hybrid-connectivity-between-skype-for-business-server-and-office-365"></a>Planejar a conectividade híbrida entre o Skype for Business Server e o Office 365

## <a name="overview"></a>Visão Geral

Leia este tópico para saber como planejar a conectividade híbrida entre o Skype for Business Server e o Teams ou o Skype for Business online. A configuração da conectividade híbrida é a primeira etapa para mover o ambiente local para a nuvem.

Se você tiver usuários do Skype for Business no local que também estejam usando o Microsoft Teams (lado a lado), esses usuários não terão a capacidade de interoperar com os usuários do Skype for Business do seu cliente do Microsoft Teams, nem se comunicar com os usuários em organizações federadas, de suas Cliente do teams. Para obter essa funcionalidade no Teams, esses usuários devem ser movidos do Skype for Business no local para a nuvem, o que requer a configuração do modo híbrido do Skype for Business. Além disso, para a melhor experiência, esses usuários devem estar no modo somente Teams, o que garante todas as chamadas de entrada e chats de qualquer usuário no cliente da equipe do usuário.

Configurar a conectividade híbrida e mover todos os usuários para a nuvem também é necessário antes de encerrar sua implantação do Skype for Business local.  Com a conectividade híbrida configurada, você pode optar por mover seus usuários para a nuvem com base em sua programação e necessidade de negócios. Com o roteamento direto, você pode aproveitar sua infraestrutura de voz local enquanto muda para a nuvem e, após a conclusão da migração.

Este tópico descreve os requisitos de infraestrutura e sistema que você precisará para configurar a conectividade híbrida entre sua implantação local do Skype for Business Server e o Microsoft Teams e o Skype for Business online existentes.

Depois de ler este tópico e estar pronto para configurar a conectividade híbrida, consulte [Configurar a conectividade híbrida entre o Skype for Business Server e o Office 365](configure-hybrid-connectivity.md). Os tópicos de configuração fornecem orientações passo a passo para configurar a conectividade híbrida entre a implantação local e o Microsoft Teams ou o Skype for Business online.

## <a name="about-shared-sip-address-space-functionality"></a>Sobre a funcionalidade de espaço de endereçamento SIP compartilhado

<a name="BKMK_Overview"> </a>

 Com a conectividade híbrida configurada entre uma implantação local do Skype for Business Server e Teams ou Skype for Business Online, você pode ter alguns usuários hospedados no local e alguns usuários hospedados online.

Esse tipo de configuração depende da funcionalidade de espaço de endereço SIP compartilhado e, às vezes, é chamada de "domínio dividido", o que significa que os usuários de um domínio, como o contoso.com, são divididos entre o uso do Skype for Business Server no local e nas equipes ou no Skype for Business Online, conforme mostrado no diagrama a seguir:

![Conectividade híbrida do SfB-domínio dividido](../../sfbserver2019/media/plan-hybrid-connectivity-2019-1.png)

Quando o espaço de endereçamento SIP compartilhado é configurado:

- O Azure Active Directory Connect é usado para sincronizar seu diretório local com o Office 365.
- Os usuários hospedados no local interagem com os servidores do Skype for Business local.
- Os usuários hospedados online podem interagir com o Skype for Business online ou com os serviços do teams.
- Os usuários de ambos os ambientes podem se comunicar entre si.
- O Active Directory local é autoritativo. Todos os usuários devem ser criados primeiro no Active Directory local e depois sincronizados com o Azure AD. Mesmo que você pretenda que o usuário seja hospedado online, você deve primeiro criar o usuário no ambiente local e, em seguida, mover o usuário para online para garantir que o usuário seja detectável por usuários locais.

Para que um usuário possa ser movido online, o usuário deve receber uma licença do Skype for Business online (plano 2). Se o usuário estiver usando o Microsoft Teams, o usuário também deverá receber uma licença do Teams (e a licença do Skype for Business deverá permanecer habilitada). Se os seus usuários desejam aproveitar recursos online adicionais, como audioconferência ou sistema de telefonia, você precisa atribuir a licença apropriada no Office 365.

## <a name="infrastructure-requirements"></a>Requisitos de infraestrutura

<a name="BKMK_Infrastructure"> </a>

Para implementar a conectividade híbrida entre seu ambiente local e os serviços de comunicação do Office 365, você precisa atender aos seguintes requisitos de infraestrutura:

- Uma única implantação local do Skype for Business Server ou do Lync Server que é implantada em uma topologia com suporte. Consulte [requisitos de topologia](plan-hybrid-connectivity.md#BKMK_Topology) neste tópico.
- Um locatário do Microsoft Office 365 com o Skype for Business online habilitado.
    > [!NOTE]
    > Você pode usar apenas um único locatário para uma configuração híbrida com sua implantação local.
- Azure Active Directory Connect para sincronizar seu diretório local com o Office 365. Para obter mais informações, consulte [Azure ad Connect: Accounts and Permissions](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-accounts-permissions).
- Ferramentas administrativas do Skype for Business Server.  Eles são necessários para mover os usuários do local para a nuvem. Essas ferramentas devem ser instaladas em um servidor com acesso à implantação local e à Internet.
- Ferramentas administrativas online.  É possível usar o centro de administração do teams ou o Windows PowerShell para gerenciar o Teams e o Skype for Business online. Para usar o PowerShell para gerenciar o Teams ou o Skype for Business Online, baixe e instale o conector do Skype for Business online.
- O espaço de endereçamento SIP compartilhado deve ser habilitado, e sua implantação local deve ser configurada para usar o Office 365 como um provedor de hospedagem. Para obter mais informações sobre as etapas necessárias para configurar a conectividade híbrida, consulte [configurar conectividade híbrida](configure-hybrid-connectivity.md).

Depois de configurar a conectividade híbrida, você pode mover os usuários para o Microsoft Teams ou o Skype for Business online. Para obter mais informações, consulte [move users from local to Teams](move-users-from-on-premises-to-teams.md) e [move users from local to Skype for Business online](move-users-from-on-premises-to-skype-for-business-online.md).

## <a name="server-version-requirements"></a>Requisitos de versão do servidor

<a name="BKMK_Topology"> </a>

Para configurar sua implantação do híbrida com o **Teams ou o Skype for Business online**, você precisa ter uma das seguintes topologias compatíveis:

- Uma implantação do Skype for Business Server 2019 com todos os servidores que executam o Skype for Business Server 2019.
- Uma implantação do Skype for Business Server 2015 com todos os servidores que executam o Skype for Business Server 2015.
- Uma implantação do Lync Server 2013 com todos os servidores que executam o Lync Server 2013.  No entanto, se a conectividade de voz híbrida for necessária, você deverá usar uma topologia de versão mista, conforme indicado a seguir.
- Uma implantação com o máximo de 2 versões de servidor diferentes, conforme listado abaixo:
  - Skype for Business Server 2015 e Skype for Business Server 2019
  - Lync Server 2013 e Skype for Business Server 2019
  - Lync Server 2013 e Skype for Business Server 2015

*Se a voz híbrida for desejada em qualquer topologia*, o servidor de borda designado como a borda de Federação, bem como o pool associado à Federação SIP, deverá estar executando o Skype for Business 2015 ou posterior. Os usuários podem permanecer em um pool do Lync 2013, se houver um. Para obter mais detalhes, consulte [Plan Phone System with PSTN Connectivity in Skype for Business Server](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity).

As seguintes topologias que incluem o **Lync Server 2010 são compatíveis com o Skype for Business online** para mensagens instantâneas e reuniões.  Topologias que incluem o **Lync Server 2010 não são suportadas para voz híbrida e equipes**.

- Uma implantação mista do Lync Server 2010 e do Skype for Business Server 2015
- Uma implantação mista do Lync Server 2010 e Lync Server 2013
- Uma implantação do Lync Server 2010 com todos os servidores que executam o Lync Server 2010 com as atualizações cumulativas mais recentes.

O servidor de borda de Federação e o servidor de próximo salto do servidor de borda de Federação devem estar executando o Lync Server 2010 com as atualizações cumulativas mais recentes. As ferramentas administrativas do Skype for Business Server 2015 ou do Lync Server 2013 devem ser instaladas em pelo menos um servidor ou estação de trabalho de gerenciamento.

## <a name="multi-forest-support"></a>Suporte a várias florestas

<a name="BKMK_MultiForest"> </a>

A Microsoft oferece suporte aos seguintes tipos de cenários híbridos de várias florestas:

- **Topologia de floresta de recursos.** Nesse tipo de topologia, há uma floresta que hospeda o Skype for Business Server (a floresta de recursos) e há uma ou mais florestas adicionais que hospedam identidades de conta, que acessam o Skype for Business Server na floresta de recursos. Em geral, os usuários podem acessar a funcionalidade do Skype for Business em outra floresta se os seguintes requisitos forem atendidos:
  - Os usuários são sincronizados corretamente na floresta que hospeda o Skype for Business. Em configurações híbridas, isso significa que os usuários devem ser sincronizados como objetos de usuário desabilitados.
  - A floresta que hospeda o Skype for Business deve confiar na floresta que contém os usuários.
    Para obter detalhes sobre cenários híbridos de floresta de recursos, consulte [implantar uma topologia de floresta de recursos para o Skype for Business híbrido](configure-a-multi-forest-environment-for-hybrid.md).
- **Várias implantações do Skype for Business Server em várias florestas.** Essa configuração pode surgir como resultado de cenários de fusão e aquisição, bem como em empresas mais complexas.  A consolidação de todos os usuários do local para a nuvem em um único locatário do Office 365 pode ser obtida para qualquer organização com várias implantações do Skype for Business, desde que os seguintes requisitos principais sejam atendidos:

  - Deve haver no máximo um locatário do Office 365 envolvido. Não há suporte para a consolidação em cenários com mais de um locatário do Office 365.
  - A qualquer momento, apenas uma floresta local do Skype for Business pode estar no modo híbrido (espaço de endereço SIP compartilhado). Todas as outras florestas do Skype for Business local devem permanecer totalmente locais (e supostamente federadas umas com as outras). Observe que essas outras organizações locais podem sincronizar com o AAD, se desejado, com [novas funcionalidades para desabilitar domínios SIP online](https://docs.microsoft.com/powershell/module/skype/disable-csonlinesipdomain) disponíveis a partir de dezembro de 2018.

    Os clientes com implantações do Skype for Business em várias florestas devem migrar totalmente cada floresta do Skype for Business individualmente para o locatário do Office 365 usando a funcionalidade de divisão de domínio (espaço de endereço SIP compartilhado) e, em seguida, desabilitar o híbrido com o implantação local, antes de passar para migrar a próxima implantação local do Skype for Business. Além disso, antes de ser migrado para a nuvem, os usuários locais permanecem em um Estado federado com qualquer usuário que não esteja representado no diretório local do mesmo usuário. Para obter mais detalhes, consulte [Cloud Consolidation for Teams and Skype for Business](cloud-consolidation.md).

## <a name="federation-requirements"></a>Requisitos de Federação

<a name="BKMK_Federation"> </a>

Ao configurar o híbrido, você deve garantir que seus ambientes locais e online possam se federar.  O ambiente online tem Federação aberta por padrão; o ambiente local geralmente tem a Federação fechada por padrão.  

Os seguintes requisitos devem ser atendidos para configurar com êxito uma implantação híbrida:

- A correspondência de domínio deve ser configurada da mesma para sua implantação local e seu locatário do Office 365. Se a descoberta de parceiros estiver habilitada na implantação local, a Federação deverá ser configurada para seu locatário online. Se a descoberta de parceiro não estiver habilitada, a Federação fechada deverá ser configurada para seu locatário online.
- A lista de domínios bloqueados na implantação local deve corresponder exatamente à lista de domínios bloqueados para seu locatário online.
- A lista de domínios permitidos na implantação local deve corresponder exatamente à lista de domínios permitidos para seu locatário online.
- A Federação deve ser habilitada para comunicações externas para o locatário online.

## <a name="network-considerations"></a>Considerações de rede

As seções a seguir descrevem as considerações para:

- Configurações de DNS
- Considerações sobre o firewall

### <a name="dns-settings"></a>Configurações de DNS

<a name="BKMK_DNS"> </a>

Ao criar registros DNS para implantações híbridas, todos os registros de DNS externos do Skype for Business devem apontar para a infraestrutura local. Para obter detalhes sobre os registros DNS necessários, consulte [DNS Requirements for Skype for Business Server](../../sfbserver/plan-your-deployment/network-requirements/dns.md).

Além disso, você precisa garantir que a resolução DNS descrita na tabela a seguir funcione em sua implantação local. (Se você já configurou a Federação para o local, então provavelmente já tem essas.)

|Registro DNS  <br/> |Resolvível por  <br/> |Requisito de DNS  <br/> |
|:-----|:-----|:-----|
|Registro SRV de DNS para _sipfederationtls. _tcp. \<sipdomain.com\> para todos os domínios SIP com suporte que resolvem os IP externos de borda de acesso  <br/> |Servidor (es) de borda  <br/> |Habilitar a comunicação federada em uma configuração híbrida. O servidor de borda precisa saber onde rotear o tráfego federado para o domínio SIP dividido entre o local e o online.  <br/> Deve usar o nome de DNS estrito correspondente entre o domínio no nome de usuário e o registro SRV.  <br/> |
|Registro (s) de DNS para o FQDN do serviço de webconferência de borda, por exemplo, webcon.contoso.com resolvendo IP (s) externo de borda de Webconferência  <br/> |Computadores de usuários conectados à rede corporativa interna  <br/> |Permitir que os usuários online apresentem ou exibam conteúdo em reuniões hospedadas no local. O conteúdo inclui arquivos do PowerPoint, quadros de comunicações, pesquisas e anotações compartilhadas.  <br/> |

Dependendo de como o DNS é configurado em sua organização, talvez seja necessário adicionar esses registros à zona de DNS hospedada internamente para o (s) domínio (s) SIP correspondente para fornecer resolução DNS interna a esses registros.

### <a name="firewall-considerations"></a>Considerações sobre o firewall

<a name="BKMK_Firewall"> </a>

Os computadores em sua rede devem ser capazes de realizar pesquisas de DNS da Internet padrão. Se estes computadores podem atingir sites da Internet padrões, sua rede cumpre este requisito.

Dependendo do local do seu data center do Microsoft Online Services, você também deve configurar seus dispositivos de firewall de rede para aceitar conexões com base em nomes de domínio curinga (por exemplo, \*todo o tráfego de. Outlook.com). Se os firewalls da sua organização não dão suporte a configurações de nome de curinga, será necessário determinar manualmente os intervalos de endereços IP que você gostaria de permitir e as portas especificadas.

Para obter mais informações, incluindo detalhes sobre as portas e os requisitos de protocolo, consulte [URLs e intervalos de endereços IP do Office 365](https://go.microsoft.com/fwlink/p/?LinkId=252942).
