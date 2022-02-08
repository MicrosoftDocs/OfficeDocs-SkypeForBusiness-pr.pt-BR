---
title: Planejar Skype for Business ambientes VDI
author: SerdarSoysal
ms.author: serdars
ms.reviewer: krishra
manager: serdars
ms.date: 1/9/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ea68414b-bb7e-483a-b731-b6b5a44372b1
description: Este tópico discute considerações de planejamento para o uso Skype for Business ao se conectar a uma área de trabalho virtual remota.
ms.openlocfilehash: 052c8b8252846204020ccb29a4d28d6150027963
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62395073"
---
# <a name="plan-for-skype-for-business-in-vdi-environments"></a>Planejar Skype for Business ambientes VDI
 
Este tópico discute considerações de planejamento para o uso Skype for Business ao se conectar a uma área de trabalho virtual remota. 
  
Um Virtual Desktop Infrastructure (VDI) é usado em algumas organizações onde os problemas de segurança e conformidade são especialmente confidenciais. Seus usuários fazem seu trabalho em uma área de trabalho virtual com todos os seus aplicativos de área de trabalho e arquivos usando Serviços de Área de Trabalho Remota ou uma conexão remota semelhante. Usar Skype for Business com áudio e vídeo completos em uma conexão como essa requer cargas pesadas de processamento de áudio e vídeo no cliente que está em uma área de trabalho virtual. Software de plug-in VDI adicional está disponível que descarrega esse processamento para a máquina local do usuário final e reduz a carga na área de trabalho virtual.
  
Há três soluções disponíveis para o componente de plug-in VDI, oferecidas pela Microsoft, Citrix ou VMWare. Para novas implantações, a Microsoft recomenda usar a solução citrix HDX RealTime Optimization Pack ou o VMWare Horizon Virtualization Pack. O Plug-in VDI do Lync original ainda tem suporte para o restante de seu ciclo de vida.
  
- O **plug-in VDI do Lync** foi desenvolvido para o Lync 2013 e é compatível com o cliente Lync 2013 ou Skype for Business 2015 em execução em uma área de trabalho virtual. É um aplicativo autônomo que instala no computador local e permite o uso de dispositivos de áudio e vídeo locais com um cliente em uma área de trabalho virtual. O plug-in não exige que um cliente Skype for Business seja instalado no computador local ou no cliente fino, que deve executar os sistemas operacionais Windows 7, Windows 8 ou Windows Server 2008. (Dispositivos cliente finos que usam esses sistemas operacionais e são compatíveis com a Microsoft incluem: Dell Wyse Z90D7, Dell Wyse R90L7, Dell Wyse X90m7, HP t610 e HP t5740e.) Esse plug-in ainda é suportado, mas nenhuma atualização futura é planejada. Para ambientes virtuais baseados em Citrix, o Citrix RealTime Optimization Pack é recomendado.
    
- O **Citrix RealTime Optimization Pack** é baseado no plug-in VDI do Lync e funciona com clientes do Lync 2013 ou Skype for Business 2016 em uma área de trabalho virtual. Ele foi desenvolvido em co-desenvolvido pelo Citrix e pela Microsoft para melhorar o Plug-in VDI original. Ele pode ser instalado em clientes com sistemas operacionais Windows e não Windows (incluindo Windows 10, Mac e Linux). Ele consiste em dois componentes: o Conector do RealTime (que está instalado na área de trabalho virtual) e o Mecanismo de Mídia do RealTime (que é instalado no computador local do usuário final). Esses dois componentes permitem que o computador local do usuário use o cliente Skype for Business em execução na área de trabalho virtual com o processamento A/V movido para o computador local. Para ambientes de área de trabalho virtuais baseados em Citrix, o Citrix RealTime Optimization Pack é recomendado e o suporte é planejado.
    
- O **VMWare Horizon Virtualization Pack** para Skype for Business, desenvolvido em colaboração com o VMWare, permite que você entregue Skype for Business em uma área de trabalho virtual ao mesmo tempo que oferece uma ótima experiência do usuário. A solução funciona aproveitando um mecanismo de mídia no cliente para criar uma solução otimizada, com o ponto de extremidade do cliente fornecendo recursos de descarregamento de mídia para chamadas de áudio e vídeo. Essa solução que pode fornecer áudio e vídeo diretamente entre os pontos de extremidade para colaboração um-a-um ou descarrega-lo para uma MCU (Unidade de Controle Multipoint) central para chamadas de conferência ou reuniões multipartidário.
    
> [!NOTE]
> Os Skype for Business básicos não têm suporte com o Pacote de Otimização do Citrix HDX RealTime ou o VMWare Horizon Virtualization Pack. 
  
## <a name="citrix-hdx-realtime-optimization-pack"></a>Citrix HDX RealTime Optimization Pack
<a name="Citrix_RT"> </a>

O plug-in de ambiente VDI do Citrix (um recurso do XenApp e XenDesktop) é compatível com os clientes Lync 2013 e Skype for Business 2015 e 2016 (clientes completos usando qualquer clique para executar o instalador ou instaladores MSI lançados após a PU de janeiro de 2017) instalados em uma área de trabalho virtual. Seu funcionamento geral é baseado no plug-in VDI do Microsoft Lync, mas funciona em uma variedade maior de sistemas operacionais cliente, incluindo Windows 10, Macintosh e Linux.
  
Uma lista completa de recursos e tecnologias com suporte pode ser encontrada no site do Citrix em [Entrega do Microsoft Skype for Business para usuários XenApp e XenDesktop](https://www.citrix.com/content/dam/citrix/en_us/documents/products-solutions/delivering-microsoft-lync-to-xenapp-and-xendesktop-users.pdf).
  
Confira os links a seguir para obter mais informações:
  
- Citrix [HDX RealTime Optimization Pack 2.1](https://docs.citrix.com/en-us/hdx-optimization/2-1.mdl)
    
- [Visão geral técnica](https://docs.citrix.com/en-us/hdx-optimization/2-1/about.mdl)
    
- [Suporte Skype for Business CTX200279](https://support.citrix.com/article/CTX200279)
    
## <a name="vmware-horizon-virtualization-pack"></a>VMWare Horizon Virtualization Pack
<a name="Citrix_RT"> </a>

A solução de ambiente VMWare do VDI é compatível com Skype for Business clientes completos de 2015 e 2016 instalados em uma área de trabalho virtual. Seu funcionamento geral é baseado no plug-in VDI do Microsoft Lync, mas funciona em uma variedade maior de sistemas operacionais cliente, incluindo Windows 10, Macintosh e Linux. 
  
Uma discussão completa sobre recursos e tecnologias com suporte pode ser encontrada no site do VMWare nos seguintes links:
  
- [Novidades no VMware Horizon 7.4 &amp; Horizon Client 4.7](https://blogs.vmware.com/euc/2018/01/vmware-horizon-7-4-horizon-client-4-7-whats-new.mdl)
    
- [Pacote de Virtualização do Horizon para Skype for Business](https://www.vmware.com/products/horizon/skype-for-business.mdl)
    
- [Microsoft Skype for Business com o VMWare Horizon](https://www.vmware.com/content/dam/digitalmarketing/vmware/en/pdf/products/horizon/vmware-skype-for-business-solution-brief.pdf)
    
## <a name="microsofts-lync-vdi-plug-in"></a>Plug-in VDI do Lync da Microsoft
<a name="Citrix_RT"> </a>

Com a solução de plug-in VDI do Microsoft Lync, o usuário precisa estar em um computador Windows ou cliente fino e ter o plug-in VDI do Lync da Microsoft instalado para lidar com fluxos de áudio/vídeo do cliente na área de trabalho virtual. Um usuário:
  
1. Conexão um dispositivo de áudio/vídeo (como um fone de ouvido ou uma câmera) para um computador local.
    
2. Conexão para uma área de trabalho virtual remota com um cliente Lync 2013 ou Skype for Business 2015.
    
3. Insira credenciais para Skype for Business na área de trabalho virtual.
    
4. Insira credenciais de usuário para estabelecer uma conexão com o plug-in VDI do Lync no computador Windows local ou no cliente fino.
    
Depois que uma conexão for estabelecida, o usuário estará pronto para fazer e receber chamadas de áudio e vídeo. O tráfego na rede e a carga na área de trabalho virtual são minimizados, pois o computador local lida com o processamento de áudio/vídeo.
  
O plug-in VDI do Lync da Microsoft só tem suporte em determinados sistemas operacionais Windows e só dá suporte a clientes do Lync 2013 ou Skype for Business 2015. Consulte [Tecnologias de virtualização com suporte e limitações conhecidas](vdi-environments.md#Supported_virt) para obter mais detalhes sobre as tecnologias e limitações suportadas.
  
Confira os links a seguir para obter mais informações:
  
- [Tecnologias de virtualização com suporte e limitações conhecidas](vdi-environments.md#Supported_virt)
    
- [Pré-requisitos de plug-in VDI do Lync](vdi-environments.md#VDI_prereq)
    
- [Implantar o plug-in VDI do Lync com Skype for Business Server](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)
    
- Artigo do Centro de Conhecimento do Citrix [CTX138408](https://support.citrix.com/article/CTX138408)
    
O plug-in do Microsoft VDI está disponível no [plug-in do Microsoft Lync VDI 2013 (32 bits)](https://www.microsoft.com/download/details.aspx?id=35457) ou no [plug-in do Microsoft Lync VDI 2013 (64 bits)](https://www.microsoft.com/download/details.aspx?id=35454). Esse plug-in é suportado com o cliente Skype for Business 2015, apesar do nome.
  
### <a name="supported-virtualization-technologies-and-known-limitations"></a>Tecnologias de virtualização com suporte e limitações conhecidas
<a name="Supported_virt"> </a>

O plug-in VDI do Lync permite a chamada de áudio e vídeo para tecnologias de virtualização com suporte. Em conformidade com os regulamentos de telefone padrão, o suporte para E911 também está incluído. As seções a seguir descrevem as tecnologias de virtualização que são suportadas pelo plug-in VDI do Lync e as limitações de recursos conhecidas.
  
#### <a name="support-for-virtualization-technologies"></a>Suporte para tecnologias de virtualização

O plug-in VDI do Lync dá suporte a sessões remotas de área de trabalho completa no cenário pessoal da área de trabalho virtual, mas não no cenário de sessão da área de trabalho remota. Esses cenários podem ser descritos da seguinte forma:
  
- **Suportado: Áreas de trabalho virtuais personalizadas ou Virtual Desktop Infrastructure (VDI).** Nesse cenário, cada usuário faz o login em uma área de trabalho virtual personalizável e é capaz de salvar arquivos na área de trabalho que persistem entre as sessões. Área de Trabalho Remota da Microsoft Serviços e VMware Horizon View são exemplos de implementações que foram testadas para uso com Skype for Business 2015. Outras implementações em validação incluem Citrix XenDesktop. Para obter informações sobre ambientes VDI específicos do fornecedor e hardware do cliente que foram testados pela Microsoft, consulte [Infraestrutura qualificada para o Microsoft Lync](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md).
    
- **Sem suporte: Sessões de Área de Trabalho Remota.** Nesse cenário, cada usuário faz o login em uma sessão de área de trabalho virtual genérica que não pode ser personalizada. Exemplos incluem Área de Trabalho Remota da Microsoft sessões (RDSH) e Citrix XenApp combinadas com o Receptor Citrix.
    
O plug-in VDI do Lync não dá suporte a outras tecnologias de virtualização, como a virtualização de aplicativos, que permite o uso de um aplicativo sem exigir a instalação do aplicativo completo localmente. As implementações de exemplo incluem Citrix XenApp e Microsoft Application Virtualization (App-V). Não há suporte para streaming de aplicativos, remoção de aplicativos e modos de virtualização mista (por exemplo, remoção de aplicativos em remoções de área de trabalho completa).
  
O plug-in VDI do Lync foi projetado para usar APIs independentes da plataforma chamadas Canais Virtuais Dinâmicos (DVCs). Para cenários que não têm suporte explícito, consulte instruções de suporte do provedor de soluções VDI.
  
#### <a name="lync-vdi-plug-in-prerequisites"></a>Pré-requisitos de plug-in VDI do Lync
<a name="VDI_prereq"> </a>

Em um ambiente VDI, as máquinas virtuais e o computador local do usuário devem atender aos requisitos descritos nesta seção.
  
> [!NOTE]
>  Seu provedor de soluções de virtualização pode fornecer detalhes sobre como instalar e implantar seu ambiente. Para obter informações gerais sobre a implantação de um ambiente virtualizado com base no Hyper-V e nos Serviços de Área de Trabalho Remota, consulte os seguintes artigos na Biblioteca da Microsoft: [Hyper-V](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753637(v=ws.10)), Serviços de Área de Trabalho Remota no [Windows Server 2008 R2](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd736539(v=ws.10)) 
  
As máquinas virtuais devem ser configuradas com Windows 8, Windows 7 ou Windows Server 2008 R2 com os service packs mais recentes.
  
O computador local do usuário deve atender aos seguintes requisitos:
  
- O usuário deve estar em casa no Skype for Business Server ou no Lync Server 2013.
    
- O computador local deve estar executando Windows Embedded Standard 7 com SP1, Windows 7 com SP1 ou Windows 8.
    
- Se você estiver usando os Serviços de Área de Trabalho Remota, escolha o plug-in VDI do Lync de 32 bits ou 64 bits para corresponder ao sistema operacional do computador local. Não é necessário que o computador local e a máquina virtual tenham sistemas operacionais de 32 ou 64 bits. Se você estiver usando outra solução ou plataforma de virtualização, consulte os requisitos do seu provedor.
    
- O computador local deve estar executando a [versão mais recente do cliente de área de trabalho remota](/windows-server/remote/remote-desktop-services/clients/remote-desktop-clients). Instale as últimas atualizações do cliente dos Serviços da Área de Trabalho Remota da Microsoft ou o software do cliente de área de trabalho remota mais atual do seu provedor de solução de virtualização. 
    
- No computador local, as configurações do cliente de área de trabalho remota devem ser definidas para que o áudio reproduza o computador local e a gravação remota esteja desabilitada. Para configurar essas configurações para a Conexão de Área de Trabalho Remota Windows, consulte a próxima seção, "Para configurar configurações de Conexão de Área de Trabalho Remota". 
    
O plug-in do Microsoft VDI está disponível no [plug-in do Microsoft Lync VDI 2013 (32 bits)](https://www.microsoft.com/download/details.aspx?id=35457) ou no [plug-in do Microsoft Lync VDI 2013 (64 bits)](https://www.microsoft.com/download/details.aspx?id=35454).
  
#### <a name="known-feature-limitations"></a>Limitações conhecidas do recurso
<a name="VDI_prereq"> </a>

A seguir estão as limitações conhecidas quando você usa o cliente Skype for Business 2015 em um ambiente VDI:
  
Há suporte limitado para recursos de Anonimato de Agente de Grupo de Resposta e Delegação de Chamada.
  
Não há suporte aos seguintes recursos:
  
- Páginas de ajuste de dispositivo de áudio integrado e dispositivo de vídeo
    
- Vídeo de exibição múltipla.
    
- Gravação de conversas.
    
- Ingressar em reuniões anonimamente (ou seja, ingressar Skype for Business reuniões hospedadas por uma organização que não se federa com sua organização).
    
- Usando o plug-in VDI do Lync juntamente com um dispositivo Lync Telefone Edition.
    
- Continuidade de chamadas em caso de indisponibilidade da rede.
    
- Toques personalizados e recursos de música em espera.
    
O plug-in VDI do Lync não é suportado em ambientes Microsoft 365 ou Office 365 ambientes.
  
> [!NOTE]
> O Citrix RealTime Optimization Pack dá suporte Microsoft 365 e Office 365. Para ambientes virtuais baseados em Citrix, consulte a documentação [](https://docs.citrix.com/en-us/hdx-optimization/2-0/hdx-realtime-optimization-pack-about.mdl) visão geral técnica da Citrix para a lista de recursos e versões com suporte.
  
## <a name="see-also"></a>Confira também
<a name="Citrix_RT"> </a>

[Implantar o plug-in VDI do Lync com Skype for Business Server](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)