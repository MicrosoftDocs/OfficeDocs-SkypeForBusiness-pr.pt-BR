---
title: Planejar a conexão híbrida | Integração do Skype for Business Server 2019 e Microsoft 365 ou Office 365
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
description: Planeje implementar a conectividade híbrida entre o Skype for Business Server e o Teams ou o Skype for Business Online configurando o modo híbrido do Skype for Business.
ms.custom: seo-marvel-jun2020
ms.openlocfilehash: 856172d5fba3df96b2456f0ceca1c661120e84e4
ms.sourcegitcommit: 43dc627e9fef31a2508f54acf741000551ff68b5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2020
ms.locfileid: "48878575"
---
# <a name="plan-hybrid-connectivity-between-skype-for-business-server-and-microsoft-365-or-office-365"></a>Planejar a conectividade híbrida entre o Skype for Business Server e o Microsoft 365 ou o Office 365

Leia este tópico para saber como planejar a conectividade híbrida entre o Skype for Business Server e o Teams ou o Skype for Business Online. Configurar a conectividade híbrida é o primeiro passo para migrar seu ambiente local para a nuvem.

Se você tem usuários do Skype for Business local que também estão usando o Teams (lado a lado), esses usuários não têm a capacidade de interoperar com os usuários do Skype for Business a partir do cliente do Teams, nem se comunicar com os usuários em organizações federadas a partir do cliente do Teams. Para obter essa funcionalidade no Teams, esses usuários devem ser movidos do Skype for Business local para a nuvem, o que requer a configuração do modo híbrido do Skype for Business. Além disso, para a melhor experiência, esses usuários devem estar no modo Apenas Teams, o que garante que todas as chamadas e chats de entrada de qualquer usuário chegam ao cliente do Teams do usuário.

Também é necessário configurar a conectividade híbrida e mover todos os usuários para a nuvem antes de você encerrar sua implantação do Skype for Business local.  Com a conectividade híbrida configurada, é possível optar por migrar os usuários para a nuvem com base na sua agenda e na necessidade de negócios. Com o Roteamento Direto, você pode aproveitar sua infraestrutura de voz local enquanto migra para a nuvem e após a conclusão da migração.

Este tópico descreve os requisitos de infraestrutura e sistema necessários para configurar a conectividade híbrida entre sua implantação local existente do Skype for Business Server e o Teams ou o Skype for Business Online.

Depois de ler este tópico e estiver pronto para configurar a conectividade híbrida, confira Configurar a conectividade híbrida entre o Skype for Business Server e o [Microsoft 365 ou Office 365.](configure-hybrid-connectivity.md) Os tópicos de configuração fornecem orientações passo a passo para configurar a conectividade híbrida entre sua implantação local e o Teams ou o Skype for Business Online.

> [!Important]
> O Skype for Business Online será retirado em 31 de julho de 2021, após o qual o serviço não estará mais acessível.  Além disso, a conectividade PSTN entre seu ambiente local, seja por meio do Skype for Business Server ou do Cloud Connector Edition e do Skype for Business Online, não terá mais suporte.  Saiba como conectar sua rede de telefonia local ao Teams usando o [Roteamento Direto.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)

## <a name="about-shared-sip-address-space-functionality"></a>Sobre a funcionalidade Espaço de Endereço SIP Compartilhado

<a name="BKMK_Overview"> </a>

 Com a conectividade híbrida configurada entre uma implantação local do Skype for Business Server e do Teams ou do Skype for Business Online, você pode ter alguns usuários instalados no local e alguns usuários online.

Esse tipo de configuração depende da funcionalidade de espaço de endereço SIP compartilhado e, às vezes, é conhecido como "domínio dividido", o que significa que os usuários de um domínio, como o contoso.com, são divididos entre usar o Skype for Business Server local e o Teams ou o Skype for Business Online, conforme mostrado no diagrama a seguir:

![Conectividade híbrida do Skype for Business - domínio dividido](../../sfbserver2019/media/plan-hybrid-connectivity-2019-1.png)

Quando o espaço de endereço SIP compartilhado está configurado:

- O Azure Active Directory Connect é usado para sincronizar seu diretório local com o Microsoft 365 ou o Office 365.
- Os usuários que estão instalados no local interagem com os servidores do Skype for Business locais.
- Os usuários que estão online podem interagir com os serviços do Skype for Business Online ou do Teams.
- Os usuários de ambos os ambientes podem se comunicar entre si.
- O Active Directory local é autoritativo. Todos os usuários devem ser criados primeiro no Active Directory local e depois sincronizados com o Azure AD. Mesmo que você pretenda que o usuário seja acessível online, primeiro você deve criar o usuário no ambiente local e, em seguida, mover o usuário para online para garantir que o usuário seja descoberto por usuários locais.

Para que um usuário possa ser movido online, ele deve ter uma licença do Skype for Business Online (Plano 2). Se o usuário for usar o Teams, o usuário também deverá receber uma licença do Teams (e a licença do Skype for Business deverá permanecer habilitada). Se os usuários quiserem aproveitar os recursos online adicionais, como Audioconferência ou Sistema de Telefonia, você precisará atribuir a eles a licença apropriada no Microsoft 365 ou No Office 365.

## <a name="hybrid-connectivity-infrastructure-requirements"></a>Requisitos de infraestrutura de conectividade híbrida

<a name="BKMK_Infrastructure"> </a>

Para implementar a conectividade híbrida entre seu ambiente local e os serviços de comunicação do Microsoft 365 ou Office 365, você precisa atender aos seguintes requisitos de infraestrutura:

- Uma implantação local única do Skype for Business Server ou do Lync Server que é implantada em uma topologia suportada. Consulte [Os requisitos de](plan-hybrid-connectivity.md#BKMK_Topology) topologia neste tópico.

- Uma organização do Microsoft 365 ou Office 365 com o Skype for Business Online habilitado.
    > [!NOTE]
    > Você pode usar apenas um único locatário para uma configuração híbrida com sua implantação local.
    
- Azure Active Directory Connect para sincronizar seu diretório local com o Microsoft 365 ou Office 365. Para saber mais, confira [Azure AD Connect: contas e permissões.](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-accounts-permissions)

- Ferramentas administrativas do Skype for Business Server. Eles são necessários para mover os usuários do local para a nuvem. Essas ferramentas devem ser instaladas em um servidor com acesso à implantação local e à Internet.
- Ferramentas administrativas online. Você pode usar o centro de administração do Teams ou o Windows PowerShell para gerenciar o Teams e o Skype for Business Online. Para usar o PowerShell para gerenciar o Teams ou o Skype for Business Online, baixe e instale o Conector do Skype for Business Online.
- O espaço de endereço SIP compartilhado deve estar habilitado, e sua implantação local deve ser configurada para usar o Microsoft 365 ou o Office 365 como um provedor de hospedagem. Para obter mais informações sobre as etapas necessárias para configurar a conectividade híbrida, consulte [Configurar conectividade híbrida.](configure-hybrid-connectivity.md)

Depois de configurar a conectividade híbrida, você pode mover os usuários para o Teams ou o Skype for Business Online. Para saber mais, [confira Mover](move-users-from-on-premises-to-teams.md) usuários do local para o Teams e mover usuários do local para o Skype for Business [Online.](move-users-from-on-premises-to-skype-for-business-online.md)

## <a name="server-version-requirements"></a>Requisitos de versão do servidor

<a name="BKMK_Topology"> </a>

Para configurar sua implantação híbrida com o Teams ou o **Skype for Business Online,** você precisa ter uma das seguintes topologias com suporte:

- Uma implantação do Skype for Business 2019 com todos os servidores executando o Skype for Business 2019.
- Uma implantação do Skype for Business 2015 com todos os servidores executando o Skype for Business 2015.
- Uma implantação do Lync Server 2013 com todos os servidores executando o Lync Server 2013.  No entanto, se a conectividade de voz híbrida for necessária, você deverá usar uma topologia de versão mista, conforme abaixo.
- Uma implantação com no máximo 2 versões diferentes de servidor, conforme listado abaixo:
  - Skype for Business Server 2015 e Skype for Business Server 2019
  - Lync Server 2013 e Skype for Business Server 2019
  - Lync Server 2013 e Skype for Business Server 2015

Se a voz híbrida for desejada em qualquer *topologia,* tanto o servidor de borda designado como Borda de Federação quanto o pool associado à federação SIP deverão estar executando o Skype for Business 2015 ou posterior. Os usuários podem permanecer em um pool do Lync 2013, se houver um. Para obter mais detalhes, [consulte Plan Phone System with PSTN Connectivity in Skype for Business Server](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity).

As topologias a seguir que incluem **o Lync Server 2010** são suportadas com o Skype for Business Online para mensagens instantâneas e reuniões. As topologias que incluem **o Lync Server 2010** não têm suporte para voz híbrida nem teams.

- Uma implantação mista do Lync Server 2010 e do Skype for Business Server 2015
- Uma implantação mista do Lync Server 2010 e do Lync Server 2013
- Uma implantação do Lync Server 2010 com todos os servidores executando o Lync Server 2010 com as atualizações cumulativas mais recentes.

O Servidor de Borda de federação e o servidor de próximo salto do Servidor de Borda de federação devem estar executando o Lync Server 2010 com as atualizações cumulativas mais recentes. As Ferramentas Administrativas do Skype for Business Server 2015 ou do Lync Server 2013 devem estar instaladas em pelo menos um servidor ou estação de trabalho de gerenciamento.

## <a name="multi-forest-support"></a>Suporte a várias florestas

<a name="BKMK_MultiForest"> </a>

A Microsoft oferece suporte aos seguintes tipos de cenários híbridos de várias florestas:

- **Topologia de floresta de recursos.** Nesse tipo de topologia, há uma floresta que hospeda o Skype for Business Server (a floresta de recursos) e há uma ou mais florestas adicionais que hospedam identidades de conta, que acessam o Skype for Business Server na floresta de recursos. Em geral, os usuários podem acessar a funcionalidade do Skype for Business em outra floresta se os seguintes requisitos são atendidos:
  - Os usuários são sincronizados corretamente na floresta que hospeda o Skype for Business. Em configurações híbridas, isso significa que os usuários devem ser sincronizados como objetos de usuário desabilitados.
  - A floresta que hospeda o Skype for Business deve confiar na floresta que contém os usuários.
    Para obter detalhes sobre cenários híbridos de floresta de recursos, consulte Implantar uma topologia de floresta de [recursos para o Skype for Business híbrido.](configure-a-multi-forest-environment-for-hybrid.md)

- **Várias implantações do Skype for Business Server em várias florestas.** Essa configuração pode surgir como resultado de cenários de fusão e aquisição, bem como em empresas mais complexas. A consolidação de todos os usuários do local para a nuvem em uma única organização do Microsoft 365 ou office 365 pode ser alcançada para qualquer organização com várias implantações do Skype for Business, desde que os seguintes requisitos principais sejam atendidos:
  - Deve haver no máximo uma organização do Microsoft 365 ou Office 365 envolvida. Não há suporte para consolidação em cenários com mais de uma organização.
  - A qualquer momento, apenas uma floresta local do Skype for Business pode estar no modo híbrido (espaço de endereço SIP compartilhado). Todas as outras florestas locais do Skype for Business devem permanecer totalmente no local (e provavelmente federadas umas com as outras). Observe que essas outras organizações locais podem sincronizar com o AAD se desejarem com novas funcionalidades para desabilitar os [domínios SIP online](https://docs.microsoft.com/powershell/module/skype/disable-csonlinesipdomain) disponíveis a partir de dezembro de 2018.

    Os clientes com implantações do Skype for Business em várias florestas devem migrar totalmente cada floresta do Skype for Business individualmente para a organização do Microsoft 365 ou Office 365 usando a funcionalidade de domínio dividido (Espaço de Endereço SIP Compartilhado) e, em seguida, desabilitar a implantação híbrida com a implantação local antes de migrar a próxima implantação local do Skype for Business. Além disso, antes de serem migrados para a nuvem, os usuários locais permanecem em um estado federado com todos os usuários que não são representados no diretório local do mesmo usuário. Para obter mais detalhes, consulte [Consolidação na nuvem para o Teams e o Skype for Business.](cloud-consolidation.md)

## <a name="federation-requirements"></a>Requisitos de federação

<a name="BKMK_Federation"> </a>

Ao configurar o modo híbrido do Skype for Business, você deve garantir que seus ambientes locais e online possam federar uns com os outros.  O ambiente online tem federação aberta por padrão; o ambiente local geralmente fecha a federação por padrão.  

Os seguintes requisitos devem ser atendidos para configurar com êxito uma implantação híbrida:

- A correspondência de domínio deve ser configurada da mesma forma para sua implantação local e sua organização do Microsoft 365 ou Office 365. Se a descoberta de parceiros estiver habilitada na implantação local, a federação aberta deverá ser configurada para sua organização online. Se a descoberta de parceiros não estiver habilitada, a federação fechada deverá ser configurada para sua organização online.
- A lista de domínios bloqueados na implantação local deve corresponder exatamente à lista de domínios bloqueados do seu locatário online.
- A lista de domínios permitidos na implantação local deve corresponder exatamente à lista de domínios permitidos para seu locatário online.
- A federação deve ser habilitada para as comunicações externas para o locatário online.

## <a name="network-considerations"></a>Considerações de rede

As seções a seguir descrevem considerações para:

- Configurações de DNS
- Considerações sobre firewall

### <a name="dns-settings-for-hybrid-deployments"></a>Configurações de DNS para implantações híbridas

<a name="BKMK_DNS"> </a>

Ao criar registros DNS para implantações híbridas, todos os registros DNS externos do Skype for Business devem apontar para a infraestrutura local. Para obter detalhes sobre os registros DNS necessários, consulte os requisitos [de DNS para o Skype for Business Server.](../../sfbserver/plan-your-deployment/network-requirements/dns.md)

Além disso, você precisa garantir que a resolução DNS descrita na tabela a seguir funcione em sua implantação local. (Se você já configurou a federação para o local, provavelmente já os tem.)

|Registro DNS  <br/> |Resolvido por  <br/> |Requisito de DNS  <br/> |
|:-----|:-----|:-----|
|Registro SRV dns para _sipfederationtls._tcp.\<sipdomain.com\> para todos os domínios SIP com suporte resolvendo IP(s) externo(s) da Borda de Acesso  <br/> |Servidor(es) de borda  <br/> |Habilitar a comunicação federada em uma configuração híbrida. O Servidor de Borda precisa saber para onde rotear o tráfego federado para o domínio SIP dividido entre o local e o online.  <br/> Deve usar uma correspondência estrita de nome DNS entre o domínio no nome de usuário e o registro SRV.  <br/> |
|Registros DNS A para FQDN do Serviço de Webconferência de Borda, por exemplo, webcon.contoso.com resolver IP externos da Borda de Webconferência  <br/> |Computadores dos usuários conectados à rede corporativa interna  <br/> |Permitir que os usuários online apresentem ou vejam conteúdo em reuniões hospedadas no local. O conteúdo inclui arquivos do PowerPoint, whiteboards, votações e anotações compartilhadas.  <br/> |

Dependendo de como o DNS está configurado em sua organização, talvez seja necessário adicionar esses registros à zona DNS hospedada interna para os domínios SIP correspondentes a fim de fornecer resolução de DNS interno a esses registros.

### <a name="firewall-considerations-for-hybrid-deployments"></a>Considerações de firewall para implantações híbridas

<a name="BKMK_Firewall"> </a>

Os computadores em sua rede devem ser capazes de executar as consultas padrão de DNS da Internet. Se estes computadores podem atingir sites da Internet padrões, sua rede cumpre este requisito.

Dependendo do local do data center do Microsoft Online Services, você também deve configurar seus dispositivos de firewall de rede para aceitar conexões com base em nomes de domínio curinga (por exemplo, todo o tráfego de \* .outlook.com). Se os firewalls da sua organização não suportam configurações de nome curinga, você terá que determinar manualmente os intervalos de endereço IP que você gostaria de permitir e as portas especificadas.

Para obter mais informações, incluindo detalhes sobre portas e requisitos de protocolo, consulte URLs e intervalos de endereços IP do [Microsoft 365 e Office 365.](https://go.microsoft.com/fwlink/p/?LinkId=252942)
