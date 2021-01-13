---
title: Planejar o Skype for Business em ambientes VDI
author: cichur
ms.author: v-cichur
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
description: Este tópico discute considerações de planejamento para usar o Skype for Business ao se conectar a uma área de trabalho virtual remota.
ms.openlocfilehash: 66fe9dd0be2dd079597837b8d25c29b3f047b0c6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816101"
---
# <a name="plan-for-skype-for-business-in-vdi-environments"></a>Planejar o Skype for Business em ambientes VDI
 
Este tópico discute considerações de planejamento para usar o Skype for Business ao se conectar a uma área de trabalho virtual remota. 
  
Um ambiente VDI (Virtual Desktop Infrastructure) é usado em algumas organizações em que os problemas de segurança e conformidade são especialmente confidenciais. Os usuários fazem seu trabalho em uma área de trabalho virtual com todos os seus aplicativos de área de trabalho e arquivos usando os Serviços de Área de Trabalho Remota ou uma conexão remota semelhante. Usar o Skype for Business com áudio e vídeo completos em uma conexão como essa exige cargas pesadas de processamento de áudio e vídeo no cliente que está em uma área de trabalho virtual. Há software de plug-in VDI adicional disponível que descarrega esse processamento para a máquina local do usuário final e reduz a carga na área de trabalho virtual.
  
Há três soluções disponíveis para o componente de plug-in VDI, oferecidas pela Microsoft, Citrix ou VMWare. Para novas implantações, a Microsoft recomenda usar a solução Citrix HDX RealTime Optimization Pack ou o VMWare Horizon Virtualization Pack. O Plug-in VDI original do Lync ainda tem suporte pelo restante de seu ciclo de vida.
  
- O **plug-in VDI do Lync** foi desenvolvido para o Lync 2013 e é compatível com o cliente Lync 2013 ou Skype for Business 2015 em execução em uma área de trabalho virtual. É um aplicativo autônomo que é instalado no computador local e permite o uso de dispositivos locais de áudio e vídeo com um cliente em uma área de trabalho virtual. O plug-in não exige que um cliente Skype for Business seja instalado no computador local ou no cliente fino, que deve executar os sistemas operacionais Windows 7, Windows 8 ou Windows Server 2008. (Dispositivos cliente finos que usam esses sistemas operacionais e são compatíveis com a Microsoft incluem: Dell Wyse Z90D7, Dell Wyse R90L7, Dell Wyse X90m7, HP t610 e HP t5740e.) Esse plug-in ainda tem suporte, mas nenhuma atualização futura está planejada. Para ambientes virtuais baseados em Citrix, o Citrix RealTime Optimization Pack é recomendado.
    
- O **Citrix RealTime Optimization Pack** é baseado no plug-in VDI do Lync e funciona com clientes do Lync 2013 ou do Skype for Business 2016 em uma área de trabalho virtual. Ele foi desenvolvido em co-desenvolvido pela Citrix e pela Microsoft para melhorar o plug-in VDI original. Ele pode ser instalado em clientes com sistemas operacionais Windows e não Windows (incluindo Windows 10, Mac e Linux). Ele consiste em dois componentes: o Conector de Tempo Real (que é instalado na área de trabalho virtual) e o RealTime Media Engine (que é instalado no computador local do usuário final). Esses dois componentes permitem que o computador local do usuário use o cliente Skype for Business em execução na área de trabalho virtual com o processamento A/V movido para o computador local. Para ambientes de área de trabalho virtual baseados em Citrix, o Citrix RealTime Optimization Pack é recomendado e há mais suporte planejado.
    
- O **VMWare Horizon Virtualization Pack** para Skype for Business, desenvolvido em colaboração com vmWare, permite que você entregue o Skype for Business em uma área de trabalho virtual, proporcionando uma excelente experiência do usuário. A solução funciona aproveitando um mecanismo de mídia no cliente para criar uma solução otimizada, com o ponto de extremidade do cliente fornecendo recursos de descarregamento de mídia para chamadas de áudio e vídeo. Esta solução pode fornecer áudio e vídeo diretamente entre os pontos de extremidade para colaboração um-em-um ou descarrega-lo para uma Unidade de Controle Multiponto (MCU) central para chamadas de conferência com vários participantes ou reuniões.
    
> [!NOTE]
> Os clientes do Skype for Business Basic não têm suporte com o Citrix HDX RealTime Optimization Pack ou o VMWare Horizon Virtualization Pack. 
  
## <a name="citrix-hdx-realtime-optimization-pack"></a>Citrix HDX RealTime Optimization Pack
<a name="Citrix_RT"> </a>

O plug-in de ambiente VDI da Citrix (um recurso do XenApp e XenDesktop) é compatível com o Lync 2013 e o Skype for Business 2015 e 2016 (clientes completos que usam qualquer clique para executar o instalador ou instaladores MSI lançados após a Atualização Pública de janeiro de 2017) instalados em uma área de trabalho virtual. Seu funcionamento geral é baseado no plug-in VDI do Microsoft Lync, mas funciona em uma variedade maior de sistemas operacionais cliente, incluindo Windows 10, Macintosh e Linux.
  
Uma lista completa de recursos e tecnologias com suporte pode ser encontrada no site da Citrix em Fornecimento do Microsoft Skype for Business para usuários [XenApp e XenDesktop.](https://www.citrix.com/content/dam/citrix/en_us/documents/products-solutions/delivering-microsoft-lync-to-xenapp-and-xendesktop-users.pdf)
  
Confira os links a seguir para obter mais informações:
  
- Citrix [HDX RealTime Optimization Pack 2.1](https://docs.citrix.com/en-us/hdx-optimization/2-1.mdl)
    
- [Visão geral técnica](https://docs.citrix.com/en-us/hdx-optimization/2-1/about.mdl)
    
- [CTX200279 Skype for Business Feature Support](https://support.citrix.com/article/CTX200279)
    
## <a name="vmware-horizon-virtualization-pack"></a>VMWare Horizon Virtualization Pack
<a name="Citrix_RT"> </a>

A solução de ambiente VDI da VMWare é compatível com clientes completos do Skype for Business 2015 e 2016 instalados em uma área de trabalho virtual. Seu funcionamento geral é baseado no plug-in VDI do Microsoft Lync, mas funciona em uma variedade maior de sistemas operacionais cliente, incluindo Windows 10, Macintosh e Linux. 
  
Uma discussão completa sobre recursos e tecnologias com suporte pode ser encontrada no site da VMWare nos seguintes links:
  
- [Novidades no VMware Horizon 7.4 &amp; Horizon Client 4.7](https://blogs.vmware.com/euc/2018/01/vmware-horizon-7-4-horizon-client-4-7-whats-new.mdl)
    
- [Pacote de Virtualização do Horizon para Skype for Business](https://www.vmware.com/products/horizon/skype-for-business.mdl)
    
- [Microsoft Skype for Business com VMWare Horizon](https://www.vmware.com/content/dam/digitalmarketing/vmware/en/pdf/products/horizon/vmware-skype-for-business-solution-brief.pdf)
    
## <a name="microsofts-lync-vdi-plug-in"></a>Plug-in VDI do Microsoft Lync
<a name="Citrix_RT"> </a>

Com a solução de plug-in VDI do Microsoft Lync, o usuário precisa estar em um computador Windows ou cliente fino e ter o plug-in VDI do Microsoft Lync instalado para manipular fluxos de áudio/vídeo do cliente na área de trabalho virtual. Um usuário irá:
  
1. Conecte um dispositivo de áudio/vídeo (como um fone de ouvido ou uma câmera) a um computador local.
    
2. Conecte-se a uma área de trabalho virtual remota com um cliente do Lync 2013 ou do Skype for Business 2015.
    
3. Insira as credenciais do Skype for Business na área de trabalho virtual.
    
4. Insira as credenciais do usuário para estabelecer uma conexão com o plug-in VDI do Lync no computador windows local ou no cliente fino.
    
Depois que uma conexão é estabelecida, o usuário está pronto para fazer e receber chamadas de áudio e vídeo. O tráfego na rede e a carga na área de trabalho virtual são minimizados, pois o computador local lida com o processamento de áudio/vídeo.
  
O plug-in VDI do Microsoft Lync só tem suporte em determinados sistemas operacionais Windows e só dá suporte a clientes do Lync 2013 ou Skype for Business 2015. Consulte [Tecnologias de virtualização suportadas e limitações conhecidas](vdi-environments.md#Supported_virt) para obter mais detalhes sobre as tecnologias e limitações com suporte.
  
Confira os links a seguir para obter mais informações:
  
- [Tecnologias de virtualização suportadas e limitações conhecidas](vdi-environments.md#Supported_virt)
    
- [Pré-requisitos de plug-in VDI do Lync](vdi-environments.md#VDI_prereq)
    
- [Implantar o plug-in VDI do Lync com o Skype for Business Server](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)
    
- Artigo do Centro de Conhecimento [Citrix CTX138408](https://support.citrix.com/article/CTX138408)
    
O plug-in VDI da Microsoft está disponível no [plug-in microsoft Lync VDI 2013 (32 bits)](https://www.microsoft.com/download/details.aspx?id=35457) ou no plug-in [do Microsoft Lync VDI 2013 (64 bits).](https://www.microsoft.com/download/details.aspx?id=35454) Esse plug-in é suportado com o cliente Skype for Business 2015, apesar do nome.
  
### <a name="supported-virtualization-technologies-and-known-limitations"></a>Tecnologias de virtualização suportadas e limitações conhecidas
<a name="Supported_virt"> </a>

O plug-in VDI do Lync permite a chamada de áudio e vídeo para tecnologias de virtualização com suporte. Em conformidade com os regulamentos de telefone padrão, o suporte para E911 também está incluído. As seções a seguir descrevem as tecnologias de virtualização que são suportadas pelo plug-in VDI do Lync e as limitações de recursos conhecidas.
  
#### <a name="support-for-virtualization-technologies"></a>Suporte para tecnologias de virtualização

O plug-in VDI do Lync dá suporte a sessões remotas de área de trabalho completas no cenário de área de trabalho virtual pessoal, mas não no cenário de sessão de área de trabalho remota. Esses cenários podem ser descritos da seguinte forma:
  
- **Com suporte: Áreas de Trabalho Virtuais Personalizadas ou Infraestrutura de Área de Trabalho Virtual (VDI).** Neste cenário, cada usuário faz o login em uma área de trabalho virtual personalizável e é capaz de salvar arquivos na área de trabalho que persistem entre sessões. Os Serviços de Área de Trabalho Remota da Microsoft e o VMware Horizon View são exemplos de implementações que foram testadas para uso com o Skype for Business 2015. Outras implementações que estão sendo validadas incluem Citrix XenDesktop. Para obter informações sobre ambientes VDI específicos do fornecedor e hardware do cliente que foram testados pela Microsoft, consulte Infraestrutura qualificada [para o Microsoft Lync.](https://go.microsoft.com/fwlink/?LinkID=313435)
    
- **Sem suporte: Sessões de Área de Trabalho Remota.** Neste cenário, cada usuário faz o login em uma sessão de área de trabalho virtual genérica que não pode ser personalizada. Exemplos incluem Sessões de Área de Trabalho Remota da Microsoft (RDSH) e Citrix XenApp combinados com o Citrix Receiver.
    
O plug-in VDI do Lync não dá suporte a outras tecnologias de virtualização, como a virtualização de aplicativos, que permite o uso de um aplicativo sem exigir a instalação do aplicativo completo localmente. Exemplos de implementações incluem Citrix XenApp e Microsoft Application Virtualization (App-V). O streaming de aplicativos, o recurso de migração remota de aplicativos e os modos de virtualização misto (por exemplo, a remotação de aplicativos em área de trabalho remota completa) não são suportados.
  
O plug-in VDI do Lync foi projetado para usar APIs independentes de plataforma chamadas DVCs (Canais Virtuais Dinâmicos). Para cenários que não têm suporte explícito, consulte as instruções de suporte do provedor de soluções VDI.
  
#### <a name="lync-vdi-plug-in-prerequisites"></a>Pré-requisitos de plug-in VDI do Lync
<a name="VDI_prereq"> </a>

Em um ambiente VDI, as máquinas virtuais e o computador local do usuário devem atender aos requisitos descritos nesta seção.
  
> [!NOTE]
>  Seu provedor de soluções de virtualização pode fornecer detalhes sobre como instalar e implantar seu ambiente. Para obter informações gerais sobre a implantação de um ambiente virtualizado baseado no Hyper-V e nos Serviços de Área de Trabalho Remota, consulte os seguintes artigos na Biblioteca da Microsoft: [Hyper-V](https://go.microsoft.com/fwlink/p/?linkid=247514), Serviços de Área de Trabalho Remota no [Windows Server 2008 R2](https://go.microsoft.com/fwlink/p/?linkid=247513) 
  
As máquinas virtuais devem ser configuradas com o Windows 8, Windows 7 ou Windows Server 2008 R2 com os service packs mais recentes.
  
O computador local do usuário deve atender aos seguintes requisitos:
  
- O usuário deve estar no Skype for Business Server ou no Lync Server 2013.
    
- O computador local deve estar executando o Windows Embedded Standard 7 com SP1, Windows 7 com SP1 ou Windows 8.
    
- Se você estiver usando os Serviços de Área de Trabalho Remota, escolha o plug-in Lync VDI de 32 bits ou 64 bits para corresponder ao sistema operacional do computador local. Não é necessário que o computador local e a máquina virtual tenham sistemas operacionais de 32 ou 64 bits. Se você estiver usando outra solução ou plataforma de virtualização, consulte os requisitos do seu provedor.
    
- O computador local deve estar executando a [versão mais recente do cliente de área de trabalho remota.](https://go.microsoft.com/fwlink/p/?LinkId=268032) Instale as últimas atualizações do cliente dos Serviços da Área de Trabalho Remota da Microsoft ou o software do cliente de área de trabalho remota mais atual do seu provedor de solução de virtualização. 
    
- No computador local, as configurações do cliente de área de trabalho remota devem ser definidas para que o áudio reproduza o computador local e a gravação remota esteja desabilitada. Para definir essas configurações para a Conexão de Área de Trabalho Remota no Windows, consulte a próxima seção, "Para definir as configurações de Conexão de Área de Trabalho Remota". 
    
O plug-in VDI da Microsoft está disponível no [plug-in microsoft Lync VDI 2013 (32 bits)](https://www.microsoft.com/download/details.aspx?id=35457) ou no plug-in [do Microsoft Lync VDI 2013 (64 bits).](https://www.microsoft.com/download/details.aspx?id=35454)
  
#### <a name="known-feature-limitations"></a>Limitações de recursos conhecidos
<a name="VDI_prereq"> </a>

Veja a seguir as limitações conhecidas quando você usa o cliente Skype for Business 2015 em um ambiente VDI:
  
Há suporte limitado para recursos de Delegação de Chamada e Anonimato do Agente do Grupo de Resposta.
  
Não há suporte aos seguintes recursos:
  
- Páginas de ajuste de dispositivo de áudio integrado e dispositivo de vídeo
    
- Vídeo com exibição múltipla.
    
- Gravação de conversas.
    
- Ingressar em reuniões anonimamente (ou seja, ingressar em reuniões do Skype for Business hospedadas por uma organização que não federa com sua organização).
    
- Usando o plug-in VDI do Lync juntamente com um dispositivo Lync Phone Edition.
    
- Continuidade de chamadas em caso de indisponibilidade da rede.
    
- Toques personalizados e recursos de música em espera.
    
O plug-in VDI do Lync não é suportado em ambientes do Microsoft 365 ou Office 365.
  
> [!NOTE]
> O Citrix RealTime Optimization Pack dá suporte ao Microsoft 365 e ao Office 365. Para ambientes virtuais baseados em Citrix, consulte a documentação de Visão Geral Técnica da Citrix para ver a lista de recursos e versões com suporte. [](https://docs.citrix.com/en-us/hdx-optimization/2-0/hdx-realtime-optimization-pack-about.mdl)
  
## <a name="see-also"></a>Confira também
<a name="Citrix_RT"> </a>

[Implantar o plug-in VDI do Lync com o Skype for Business Server](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)

