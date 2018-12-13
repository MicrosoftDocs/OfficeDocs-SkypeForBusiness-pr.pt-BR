---
title: Planejar a conectividade híbrida
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Considerações de planejamento para a implementação de conectividade híbrida entre Skype para Business Server e do Skype para Business Online ou equipes.
ms.openlocfilehash: ef74a0b2dcc4943b5e95ddd8ba15005e50ec6cd6
ms.sourcegitcommit: 4dac1994b829d7a7aefc3c003eec998e011c1bd3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/13/2018
ms.locfileid: "27244022"
---
# <a name="plan-hybrid-connectivity-between-skype-for-business-server-and-office-365"></a>Planejar a conectividade híbrida entre Skype para Business Server e Office 365

## <a name="overview"></a>Visão geral

Leia este tópico para saber como planejar a conectividade híbrida entre Skype para servidor de negócios e equipes ou Skype para negócios Online. Configurar a conectividade híbrida é a primeira etapa na migração do seu ambiente local para a nuvem.

Se você tiver Skype local para usuários corporativos também usando equipes (lado a lado), esses usuários não têm a capacidade de interoperar com Skype para usuários de negócios do cliente suas equipes, nem se comunicar com usuários em organizações federadas, seus Cliente de equipes. Para obter essa funcionalidade em equipes, esses usuários devem ser movidos do Skype para negócios local para a nuvem, que requer configuração Skype para modo híbrido de negócios. Além disso, para uma melhor experiência, esses usuários devem estar no equipes somente modo, que garante que todas as chamadas recebidas e chats de qualquer land do usuário no cliente de equipes do usuário.

Configurando a conectividade híbrida e mover todos os usuários para a nuvem também são necessária antes de encerrar sua Skype local para implantação de negócios.  Com a conectividade híbrida configurada, você pode escolher mover os usuários para a nuvem com base em sua necessidade de agenda e corporativos. Com o roteamento direto, você pode aproveitar sua infraestrutura de voz no local enquanto você move para a nuvem e depois que a migração estiver concluída.

Este tópico descreve a infraestrutura e os requisitos de sistema, você precisará configurar a conectividade híbrida entre as existentes no local Skype para implantação de servidor de negócios e equipes ou Skype para Business Online.

Depois que você leia este tópico e estiver pronto para configurar a conectividade híbrida, consulte [Configure a conectividade de híbrido entre Skype para Business Server e Office 365](configure-hybrid-connectivity.md). Os tópicos de configuração fornecem orientação passo a passo para configurar a conectividade híbrida entre sua implantação no local e equipes ou Skype para negócios Online.


## <a name="about-shared-sip-address-space-functionality"></a>Sobre a funcionalidade de espaço de endereçamento SIP compartilhado
<a name="BKMK_Overview"> </a>

 Com a conectividade híbrida configurada entre uma implantação local do Skype para servidor de negócios e equipes ou Skype para Business Online, você pode ter alguns usuários hospedados no local e alguns usuários hospedagem online.

Esse tipo de configuração depende da funcionalidade de espaço de endereço SIP compartilhada e às vezes é conhecido como "domínio dividido" – que significa que os usuários de um domínio, por exemplo, contoso.com, são divididos entre usando Skype para Business Server no local e as equipes ou Skype para negócios On-line, conforme mostrado no diagrama a seguir: 

![Conectividade híbrida do SfB - domínio dividido](../../sfbserver2019/media/plan-hybrid-connectivity-2019-1.png)

Quando o espaço de endereçamento SIP compartilhado está configurado:

- Azure Active Directory se conectar é usado para sincronizar seu diretório local com o Office 365.
- Os usuários hospedados no local interagem com Skype local para os servidores de negócios. 
- Os usuários hospedados online podem interagir com Skype para equipes ou Business Online services.
- Os usuários de ambos os ambientes podem se comunicar entre si. 
- O Active Directory local é autoritativo. Todos os usuários devem ser criados no Active Directory local primeiro e, em seguida, sincronizados com o Azure AD. Mesmo se você pretende que o usuário a ser hospedados online, você deve primeiro criar o usuário no ambiente local e mova o usuário para on-line para garantir que o usuário é descoberto pelos usuários no local. 

Antes de um usuário pode ser movido online, o usuário deve ser atribuído a um Skype licença Business Online (plano 2). Se o usuário for usar equipes, o usuário também deve ser atribuído uma licença de equipes (e o Skype licença de negócios deve permanecer habilitado). Se quiserem que seus usuários para se beneficiar dos recursos online adicionais, como conferência de áudio ou o sistema telefônico, você precisará atribuí-las a licença apropriada no Office 365.


## <a name="infrastructure-requirements"></a>Requisitos de infraestrutura
<a name="BKMK_Infrastructure"> </a>

Para implementar a conectividade híbrida entre seu ambiente local e serviços de comunicação do Office 365, você precisa atender aos seguintes requisitos de infraestrutura:

- Uma única implantação do Skype para Business Server ou o Lync Server é implantado em uma topologia com suporte no local. Consulte [requisitos de topologia](plan-hybrid-connectivity.md#BKMK_Topology) neste tópico.
- Um inquilino do Microsoft Office 365 com o Skype para Business Online habilitado.
    > [!NOTE]
    > Você só pode usar um único locatário para uma configuração híbrida com sua implantação local.
- Azure Active Directory Connect para sincronizar seu diretório local com o Office 365. Para obter mais informações, consulte [Connect do Azure AD: contas e permissões](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect-accounts-permissions).
- Skype para ferramentas administrativas do servidor de negócios.  Eles são exigidos para mover usuários do local para a nuvem. Essas ferramentas devem ser instaladas em um servidor com acesso à implantação no local e a internet. 
- Ferramentas administrativas online.  Você pode usar as equipes e o Skype para o Centro de administração de negócios ou o Windows PowerShell para gerenciar equipes e Skype para Business Online. Para usar o PowerShell para gerenciar equipes ou Skype para Business Online, baixe e instale o Skype para o Business Connector Online. 
- Espaço de endereçamento SIP compartilhado deve ser habilitado e sua implantação no local deve ser configurada para usar o Office 365 como um provedor de hospedagem. Para obter mais informações sobre as etapas necessárias para configurar a conectividade híbrida, consulte [Configure conectividade de híbrida](configure-hybrid-connectivity.md).

Depois de configurar conectividade híbrida, você pode mover usuários para equipes ou Skype para negócios Online. Para obter mais informações, consulte [mover usuários no local para equipes](move-users-from-on-premises-to-teams.md) e [mover os usuários no local para Skype para negócios Online](move-users-from-on-premises-to-skype-for-business-online.md).


## <a name="server-version-requirements"></a>Requisitos de versão do servidor
<a name="BKMK_Topology"> </a>

Para configurar sua implantação para o híbrido com **equipes ou Skype para Business Online**, você precisa ter uma das seguintes topologias com suporte:

- Um Skype para implantação de negócios Server 2019 com todos os servidores que executam o Skype para Business Server 2019. 
- Um Skype para implantação de negócios Server 2015 com todos os servidores que executam o Skype para Business Server 2015.
- Uma implantação do Lync Server 2013 com todos os servidores que executam o Lync Server 2013.  No entanto, se é necessária a conectividade de voz de híbrido, você deve usar uma topologia de versão mista conforme observado abaixo.
- Uma implantação com o máximo de 2 versões de servidor diferentes, como listadas abaixo:
  - Skype para Business Server 2015 e Skype para Business Server 2019
  - Lync Server 2013 e Skype para Business Server 2019
  - Lync Server 2013 e Skype para Business Server 2015

*Se a voz híbrida for desejada em qualquer topologia*, o servidor de borda que é designado como a borda de federação, bem como o pool associado a federação SIP deve estar executando o Skype para negócios 2015 ou posterior. Os usuários podem permanecer em um Pool do Lync 2013, se houver uma. Para obter mais detalhes, consulte [Planejar o sistema de telefone com conectividade PSTN em Skype para Business Server](https://docs.microsoft.com/en-us/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity).

As seguintes topologias que incluem o **Lync Server 2010 são compatíveis com o Skype para Business Online** para mensagens instantâneas e reuniões.  Topologias que incluem o **Lync Server 2010 não são suportadas para voz híbrida nem equipes**.

- Um misto Lync Server 2010 e Skype para implantação Business Server 2015
- Uma implantação mista do Lync Server 2010 e Lync Server 2013
-   Uma implantação do Lync Server 2010 com todos os servidores que executam o Lync Server 2010 com as últimas atualizações acumuladas.
O servidor de borda de Federação e o servidor de próximo salto da federação servidor de borda devem estar executando o Lync Server 2010 com as últimas atualizações acumuladas. O Skype para Business Server 2015 ou o Lync Server 2013 Administrative Tools deve ser instalado em pelo menos um servidor ou estação de trabalho de gerenciamento.



 ## <a name="multi-forest-support"></a>Suporte a várias florestas
<a name="BKMK_MultiForest"> </a>

Microsoft suporta os seguintes tipos de cenários híbridos de várias florestas:

- **Topologia de floresta de recursos.** Nesse tipo de topologia, há uma floresta que hospeda o Skype para Business Server (a floresta de recursos) e há um ou mais florestas adicionais que identidades de conta de host, que acessar o Skype para Business Server na floresta de recursos. Em geral, os usuários podem acessar Skype para a funcionalidade de negócios em outra floresta se os seguintes requisitos são atendidos:
    - Os usuários adequadamente são sincronizados para a floresta que hospeda Skype para negócios. Configurações híbridas, isso significa que os usuários devem ser sincronizados como objetos de usuário desabilitadas.
    - A floresta que hospeda o Skype for Business deve confiar na floresta que contém os usuários.
    Para obter detalhes sobre cenários de híbrido de floresta de recursos, consulte [Deploy uma topologia de floresta de recursos para o híbrido Skype para negócios](configure-a-multi-forest-environment-for-hybrid.md).
- **Várias implantações do Skype para Business Server em várias florestas.** Essa configuração pode surgir como resultado de cenários de fusão e aquisição, bem como em empresas mais complexas.  A consolidação de todos os usuários no local para a nuvem em um único locatário do Office 365 pode ser alcançada para qualquer organização com vários Skype para implantações de negócios, desde que os principais requisitos a seguintes são atendidos: 
    - Deve haver no máximo um locatário do Office 365 envolvidos. Não há suporte para a consolidação em cenários com mais de um inquilino do Office 365.
    - A qualquer momento determinado, somente um local Skype para a floresta de negócios pode estar em modo híbrido (espaço de endereçamento SIP compartilhado). Todos os outro Skype local para florestas de negócios deve permanecer totalmente no local (e possivelmente federados uns com os outros). Observe que essas organizações do local podem sincronizar com o AAD se desejar com [novas funcionalidades para desabilitar os domínios SIP on-line](https://docs.microsoft.com/en-us/powershell/module/skype/disable-csonlinesipdomain) disponível a partir de dezembro de 2018.

    Clientes com implantações do Skype para negócios em várias florestas devem totalmente migrar cada Skype para a floresta de negócios individualmente para o inquilino do Office 365 usando a funcionalidade de divisão de domínios (Shared a espaço de endereço SIP) e, em seguida, desabilitar híbrida com o implantação no local, antes de seguir adiante para migrar o próximo local Skype para implantação de negócios. Além disso, antes de serem migrados para a nuvem, usuários locais permanecem em um estado federado com todos os usuários que não são representados no diretório local mesmo do usuário. Para obter mais detalhes, consulte [consolidação de nuvem para equipes e Skype para negócios](cloud-consolidation.md).



## <a name="federation-requirements"></a>Requisitos de Federação
<a name="BKMK_Federation"> </a>

Ao configurar híbrido, você deve garantir que sua organização local e ambientes on-line podem federar uns com os outros.  O ambiente online tem federação aberta por padrão. o ambiente local frequentemente fechou federação por padrão.  

Os seguintes requisitos devem ser atendidos para configurar com êxito uma implantação híbrida:

- O domínio correspondente deve ser o mesmo configurado para sua implantação local e seu locatário do Office 365. Se a descoberta de parceiros estiver habilitada na implantação local, a federação aberta deverá ser configurada para seu locatário online. Caso contrário, a federação fechada deverá ser configurada para seu locatário online.
- A lista de domínios bloqueados da implantação local deve corresponder exatamente à do seu locatário online.
- A lista de domínios permitidos da implantação local deve corresponder exatamente à do seu locatário online.
- Federação deve ser habilitada para as comunicações externas para o locatário online.


## <a name="network-considerations"></a>Considerações de rede

As seções a seguir descrevem as considerações para: 

- Configurações de DNS 
- Considerações sobre o firewall 


### <a name="dns-settings"></a>Configurações de DNS
<a name="BKMK_DNS"> </a>

Ao criar registros DNS para implantações híbridas, todos os Skype para registros DNS externos corporativos deve apontar para a infraestrutura local. Para obter detalhes sobre registros DNS necessários, consulte [requisitos de DNS para Skype para Business Server](../../sfbserver/plan-your-deployment/network-requirements/dns.md).

Além disso, você precisará garantir que a resolução de DNS descrita na tabela a seguir funciona em sua implantação no local. (Se você já configurou a federação para o local, em seguida, você provavelmente já ter.)

|Registro DNS  <br/> |Pode ser resolvido por  <br/> |Requisitos de DNS  <br/> |
|:-----|:-----|:-----|
|Registro SRV de DNS para _sipfederationtls._tcp. \<sipdomain.com\> para todas as compatíveis domínios SIP resolver em IP(s) de borda de acesso externo  <br/> |Servidor(es) de borda  <br/> |Habilitar a comunicação federada em uma configuração híbrida. O servidor de borda precisa saber para onde encaminhar o tráfego federado para o domínio SIP que está dividido entre as instalações local e online.  <br/> Deve usar uma correspondência estrita de nomes DNS entre o domínio no nome de usuário e o registro SRV.  <br/> |
|Registro(s) A de DNS para FQDN do serviço de webconferência de borda, como webcon.contoso.com, que resolve IP(s) de borda de webconferência  <br/> |Rede corporativa interna conectados nos computadores dos usuários  <br/> |Habilitar usuários online para apresentar ou visualizar conteúdo em reuniões hospedadas localmente. O conteúdo inclui arquivos do PowerPoint, quadros de comunicações, votações e observações compartilhadas.   <br/> |

Dependendo de como o DNS está configurado na sua organização, talvez seja necessário adicionar esses registros à zona DNS hospedada interna para os domínios SIP correspondentes para proporcionar resolução de DNS interna para esses registros. 

### <a name="firewall-considerations"></a>Considerações sobre o firewall
<a name="BKMK_Firewall"> </a>

Os computadores de sua rede devem ser capazes de realizar pesquisas DNS padrão na Internet. Se esses computadores puderem acessar os sites padrão da Internet, sua rede atenderá a esse requisito.

Dependendo do local do seu centro de dados do Microsoft Online Services, você também deve configurar os dispositivos de firewall de rede para aceitar conexões com base em nomes de domínio de caractere curinga (por exemplo, todo o tráfego da \*. outlook.com). Se dos firewalls da organização não oferecer suporte a configurações de nome de curinga, você terá de determinar manualmente os intervalos de endereços IP que você gostaria de permitir e as portas especificadas.

Para obter mais informações, incluindo detalhes sobre portas e os requisitos de protocolo, consulte [URLs do Office 365 e intervalos de endereços IP](https://go.microsoft.com/fwlink/p/?LinkId=252942).
