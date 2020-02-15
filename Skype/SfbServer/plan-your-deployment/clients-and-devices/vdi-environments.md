---
title: Planejar o Skype for Business em ambientes de VDI
author: lanachin
ms.author: v-lanac
ms.reviewer: krishra
manager: serdars
ms.date: 1/9/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ea68414b-bb7e-483a-b731-b6b5a44372b1
description: Este tópico discute considerações de planejamento para usar o Skype for Business enquanto se conecta a uma área de trabalho remota virtual.
ms.openlocfilehash: c2972e2b453b6cf5592ddc8b3b48dfceee9a4e35
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42027992"
---
# <a name="plan-for-skype-for-business-in-vdi-environments"></a>Planejar o Skype for Business em ambientes de VDI
 
Este tópico discute considerações de planejamento para usar o Skype for Business enquanto se conecta a uma área de trabalho remota virtual. 
  
Um ambiente de infraestrutura de área de trabalho virtual (VDI) é usado em algumas organizações onde problemas de segurança e conformidade são especialmente confidenciais. Seus usuários trabalham em uma área de trabalho virtual com todos os seus aplicativos e arquivos de área de trabalho usando os serviços de área de trabalho remota ou uma conexão remota semelhante. O uso do Skype for Business com áudio e vídeo completos em uma conexão como o requer cargas pesadas de processamento de áudio e vídeo no cliente hospedado em uma área de trabalho virtual. Está disponível um software adicional de plug-in VDI que descarrega o processamento para o computador local do usuário final e reduz a carga na área de trabalho virtual.
  
Há três soluções disponíveis para o componente de plug-in VDI, oferecido pela Microsoft, Citrix ou VMWare. Para novas implantações, a Microsoft recomenda o uso da solução de pacote de otimização do Citrix HDX em tempo real ou do pacote de virtualização do VMWare horizonte. O plug-in do Lync VDI original ainda tem suporte para o restante do seu ciclo de vida.
  
- O **plug-in de VDI do Lync** foi desenvolvido para o Lync 2013 e é compatível com o cliente do Lync 2013 ou do Skype for Business 2015 em execução em uma área de trabalho virtual. É um aplicativo autônomo que é instalado no computador local e permite o uso de dispositivos de áudio e vídeo locais com um cliente em uma área de trabalho virtual. O plug-in não requer que um cliente do Skype for Business seja instalado no computador local ou cliente fino, que deve executar os sistemas operacionais Windows 7, Windows 8 ou Windows Server 2008. (Os dispositivos de cliente fino que usam esses sistemas operacionais e suportados pela Microsoft incluem: Dell Wyse Z90D7, Dell Wyse R90L7, Dell Wyse X90m7, HP T610 e HP t5740e.) Esse plug-in ainda tem suporte, mas nenhuma atualização futura é planejada. Para ambientes virtuais baseados em Citrix, o pacote de otimização do Citrix RealTime é recomendado.
    
- O **pacote de otimização do Citrix Realtime** é criado no plug-in do Lync VDI e funciona com clientes do Lync 2013 ou do Skype for Business 2016 em uma área de trabalho virtual. Ele foi desenvolvido em conjunto pela Citrix e pela Microsoft para melhorar a partir do plug-in VDI original. Ele pode ser instalado em clientes com sistemas operacionais Windows e não Windows (incluindo Windows 10, Mac e Linux). Ele consiste em dois componentes: o conector em tempo real (que é instalado na área de trabalho virtual) e o mecanismo de mídia em tempo real (que é instalado no computador local do usuário final). Esses dois componentes permitem que o computador local do usuário use o cliente Skype for Business em execução na área de trabalho virtual com o processamento de A/V movido para o computador local. Para ambientes de área de trabalho virtual baseados em Citrix, o pacote de otimização do Citrix RealTime é recomendado e o suporte adicional é planejado.
    
- O **pacote de virtualização do VMware horizonte** para o Skype for Business, desenvolvido em colaboração com o VMware, permite que você forneça o Skype for Business em uma área de trabalho virtual ao mesmo tempo que oferece uma ótima experiência do usuário. A solução funciona utilizando um mecanismo de mídia no cliente para criar uma solução otimizada, com o ponto de extremidade do cliente fornecendo recursos de descarregamento de mídia para chamadas de áudio e vídeo. Esta solução pode fornecer áudio e vídeo diretamente entre os pontos de extremidade de uma colaboração de uma em um ou o transfere para uma unidade de controle multiponto (MCU) central para chamadas ou reuniões de conferência de vários participantes.
    
> [!NOTE]
> Os clientes do Skype for Business Basic não são compatíveis com o pacote de otimização em tempo real do Citrix HDX ou o pacote de virtualização do VMWare horizonte. 
  
## <a name="citrix-hdx-realtime-optimization-pack"></a>Pacote de otimização do Citrix HDX em tempo real
<a name="Citrix_RT"> </a>

O plug-in do ambiente VDI do Citrix (um recurso do XenApp e do XenDesktop) é compatível com o Lync 2013 e o Skype for Business 2015 e 2016 (clientes completos usando qualquer clique para executar o instalador ou instaladores MSI lançados após os clientes de janeiro de 2017) instalados em um virtual placa. O funcionamento geral é baseado no plug-in VDI do Microsoft Lync, mas funciona em uma variedade maior de sistemas operacionais clientes, incluindo Windows 10, Macintosh e Linux.
  
Uma lista completa de recursos e tecnologias compatíveis pode ser encontrada no site da Citrix na [entrega do Microsoft Skype for Business para usuários do XenApp e do XenDesktop](https://www.citrix.com/content/dam/citrix/en_us/documents/products-solutions/delivering-microsoft-lync-to-xenapp-and-xendesktop-users.pdf).
  
Confira os seguintes links para obter mais informações:
  
- Pacote de otimização do Citrix [HDX em tempo real 2,1](https://docs.citrix.com/en-us/hdx-optimization/2-1.mdl)
    
- [Visão geral técnica](https://docs.citrix.com/en-us/hdx-optimization/2-1/about.mdl)
    
- [Suporte de recursos do Skype for Business CTX200279](https://support.citrix.com/article/CTX200279)
    
## <a name="vmware-horizon-virtualization-pack"></a>Pacote de virtualização do VMWare horizonte
<a name="Citrix_RT"> </a>

A solução de ambiente VDI do VMWare é compatível com clientes completos do Skype for Business 2015 e 2016 instalados em uma área de trabalho virtual. O funcionamento geral é baseado no plug-in VDI do Microsoft Lync, mas funciona em uma variedade maior de sistemas operacionais clientes, incluindo Windows 10, Macintosh e Linux. 
  
Uma discussão completa de recursos e tecnologias compatíveis pode ser encontrada no site do VMWare nos seguintes links:
  
- [O que há de novo no VMware &amp; horizonte 7,4 horizonte Client 4,7](https://blogs.vmware.com/euc/2018/01/vmware-horizon-7-4-horizon-client-4-7-whats-new.mdl)
    
- [Horizonte Virtualization Pack para Skype for Business](https://www.vmware.com/products/horizon/skype-for-business.mdl)
    
- [Microsoft Skype for Business com VMWare horizonte](https://www.vmware.com/content/dam/digitalmarketing/vmware/en/pdf/products/horizon/vmware-skype-for-business-solution-brief.pdf)
    
## <a name="microsofts-lync-vdi-plug-in"></a>Plug-in VDI do Lync da Microsoft
<a name="Citrix_RT"> </a>

Com a solução de plug-in VDI do Microsoft Lync, o usuário precisa estar em um computador com o Windows ou cliente fino e ter o plug-in VDI do Lync da Microsoft instalado para lidar com fluxos de áudio/vídeo do cliente na área de trabalho virtual. Um usuário irá:
  
1. Conecte um dispositivo de áudio/vídeo (como um headset ou uma câmera) a um computador local.
    
2. Conecte-se a uma área de trabalho virtual remota com um cliente 2015 Lync 2013 ou Skype for Business.
    
3. Insira as credenciais do Skype for Business na área de trabalho virtual.
    
4. Insira novamente as credenciais do usuário para estabelecer uma conexão com o plug-in VDI do Lync no computador local do Windows ou cliente fino.
    
Depois que uma conexão for estabelecida, o usuário estará pronto para fazer e receber chamadas de áudio e vídeo. O tráfego na rede e a carga na área de trabalho virtual são minimizados, pois o computador local manipula o processamento de áudio/vídeo.
  
O plug-in VDI do Lync da Microsoft só tem suporte em determinados sistemas operacionais Windows e só oferece suporte aos clientes do Lync 2013 ou Skype for Business 2015. Consulte [tecnologias de virtualização suportadas e limitações conhecidas](vdi-environments.md#Supported_virt) para obter mais detalhes sobre tecnologias e limitações suportadas.
  
Confira os seguintes links para obter mais informações:
  
- [Tecnologias de virtualização suportadas e limitações conhecidas](vdi-environments.md#Supported_virt)
    
- [Pré-requisitos do plug-in VDI do Lync](vdi-environments.md#VDI_prereq)
    
- [Implantar o plug-in de VDI do Lync com o Skype for Business Server](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)
    
- Artigo [CTX138408](https://support.citrix.com/article/CTX138408) da central de conhecimento da Citrix
    
O plug-in VDI da Microsoft está disponível em [Microsoft LYNC vdi 2013 plugin (32 bit)](https://www.microsoft.com/download/details.aspx?id=35457) ou [microsoft Lync VDI 2013 plugin (64 bit)](https://www.microsoft.com/download/details.aspx?id=35454). Esse plug-in é compatível com o cliente do Skype for Business 2015, apesar do nome.
  
### <a name="supported-virtualization-technologies-and-known-limitations"></a>Tecnologias de virtualização suportadas e limitações conhecidas
<a name="Supported_virt"> </a>

O plug-in de VDI do Lync permite chamadas de áudio e vídeo para tecnologias de virtualização suportadas. Em conformidade com as regulamentações de telefone padrão, o suporte para o E911 também está incluído. As seções a seguir descrevem as tecnologias de virtualização compatíveis com o plug-in VDI do Lync e as limitações de recursos conhecidas.
  
#### <a name="support-for-virtualization-technologies"></a>Suporte para tecnologias de virtualização

O plug-in do Lync VDI oferece suporte a sessões remotas completas de área de trabalho no cenário de área de trabalho virtual pessoal, mas não no cenário de sessão de área de trabalho remota. Esses cenários podem ser descritos da seguinte maneira:
  
- **Com suporte: áreas de trabalho virtuais personalizadas ou VDI (Virtual Desktop Infrastructure).** Neste cenário, cada usuário faz logon em uma área de trabalho virtual personalizável e pode salvar arquivos na área de trabalho que persistem entre as sessões. Os serviços de área de trabalho remota da Microsoft e o modo de exibição de horizonte do VMware são implementações que foram testadas para uso com o Skype for Business 2015. Outras implementações que estão sendo validadas incluem Citrix XenDesktop. Para obter informações sobre ambientes VDI específicos do fornecedor e hardware de cliente que foram testados pela Microsoft, consulte [infraestrutura qualificada para Microsoft Lync](https://go.microsoft.com/fwlink/?LinkID=313435).
    
- **Sem suporte: sessões da área de trabalho remota.** Neste cenário, cada usuário faz logon em uma sessão de área de trabalho virtual genérica que não pode ser personalizada. Os exemplos incluem sessões da área de trabalho remota da Microsoft (RDSH) e Citrix XenApp combinados com o receptor Citrix.
    
O plug-in do Lync VDI não oferece suporte a outras tecnologias de virtualização, como a virtualização de aplicativo, que permite o uso de um aplicativo sem exigir a instalação do aplicativo completo localmente. As implementações de exemplo incluem o Citrix XenApp e o Microsoft Application Virtualization (App-V). Não há suporte para o fluxo de aplicativos, comunicação remota de aplicativos e modos de virtualização mista (por exemplo, aplicativos remotos de área de trabalho remota).
  
O plug-in do Lync VDI foi projetado para usar APIs independentes de plataforma chamadas DVCs (canais virtuais dinâmicos). Para cenários que não são explicitamente suportados, consulte instruções de suporte do provedor de soluções VDI.
  
#### <a name="lync-vdi-plug-in-prerequisites"></a>Pré-requisitos do plug-in VDI do Lync
<a name="VDI_prereq"> </a>

Em um ambiente VDI, as máquinas virtuais e o computador local do usuário devem atender aos requisitos descritos nesta seção.
  
> [!NOTE]
>  Seu provedor de soluções de virtualização pode fornecer detalhes sobre como instalar e implantar seu ambiente. Para obter informações gerais sobre a implantação de um ambiente virtualizado com base nos serviços de área de trabalho remota e Hyper-V, consulte os seguintes artigos na biblioteca da Microsoft: [Hyper-v](https://go.microsoft.com/fwlink/p/?linkid=247514), [serviços de área de trabalho remota no Windows Server 2008 R2](https://go.microsoft.com/fwlink/p/?linkid=247513) 
  
As máquinas virtuais devem ser configuradas com Windows 8, Windows 7 ou Windows Server 2008 R2 com os service packs mais recentes.
  
O computador local do usuário deve atender aos seguintes requisitos:
  
- O usuário deve estar hospedado no Skype for Business Server ou no Lync Server 2013.
    
- O computador local deve estar executando o Windows Embedded Standard 7 com SP1, o Windows 7 com SP1 ou o Windows 8.
    
- Se você estiver usando os serviços de área de trabalho remota, escolha o plug-in do Lync VDI de 32 bits ou 64 bits para corresponder ao sistema operacional do computador local. Não é necessário que o computador local e a máquina virtual tenham sistemas operacionais de 32 bits ou 64 bits. Se você estiver usando outra solução ou plataforma de virtualização, consulte os requisitos do provedor.
    
- O computador local deve estar executando a [versão mais recente do cliente da área de trabalho remota](https://go.microsoft.com/fwlink/p/?LinkId=268032). Instale as últimas atualizações do cliente dos Serviços da Área de Trabalho Remota da Microsoft ou o software do cliente de área de trabalho remota mais atual do seu provedor de solução de virtualização. 
    
- No computador local, as configurações do cliente de área de trabalho remota devem ser definidas para que o áudio reproduza o computador local e a gravação remota esteja desabilitada. Para definir essas configurações para a conexão de área de trabalho remota no Windows, confira a próxima seção, "para definir as configurações da conexão de área de trabalho remota". 
    
O plug-in VDI da Microsoft está disponível em [Microsoft LYNC vdi 2013 plugin (32 bit)](https://www.microsoft.com/download/details.aspx?id=35457) ou [microsoft Lync VDI 2013 plugin (64 bit)](https://www.microsoft.com/download/details.aspx?id=35454).
  
#### <a name="known-feature-limitations"></a>Limitações de recursos conhecidos
<a name="VDI_prereq"> </a>

Os itens a seguir são limitações conhecidas quando você usa o cliente 2015 do Skype for Business em um ambiente de VDI:
  
Há suporte limitado para recursos de delegação de chamada e de anonimato de agente do grupo de resposta.
  
Não há suporte aos seguintes recursos:
  
- Páginas de ajuste de dispositivo de áudio integrado e dispositivo de vídeo
    
- Vídeo de várias exibições.
    
- Gravação de conversas.
    
- Ingressar em reuniões anonimamente (ou seja, ingressar em reuniões do Skype for Business hospedadas por uma organização que não se federa à sua organização).
    
- Usando o plug-in do Lync VDI junto com um dispositivo do Lync Phone Edition.
    
- Continuidade de chamadas em caso de indisponibilidade da rede.
    
- Toques personalizados e recursos de música em espera.
    
O plug-in do Lync VDI não é suportado em um ambiente do Office 365.
  
> [!NOTE]
> O pacote de otimização do Citrix RealTime oferece suporte ao Office 365. Para ambientes virtuais baseados em Citrix, revise a documentação de [visão geral técnica](https://docs.citrix.com/en-us/hdx-optimization/2-0/hdx-realtime-optimization-pack-about.mdl) da Citrix para obter a lista de recursos e versões compatíveis.
  
## <a name="see-also"></a>Confira também
<a name="Citrix_RT"> </a>

[Implantar o plug-in de VDI do Lync com o Skype for Business Server](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)

