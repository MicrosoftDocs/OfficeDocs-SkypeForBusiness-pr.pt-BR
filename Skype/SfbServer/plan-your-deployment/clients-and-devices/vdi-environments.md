---
title: Planejar para o Skype for Business em ambientes VDI
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 1/9/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ea68414b-bb7e-483a-b731-b6b5a44372b1
description: Este tópico aborda considerações de planejamento para uso do Skype for Business durante a conexão a uma área de trabalho remota virtual.
ms.openlocfilehash: 2b682b010211f46ebd405131ed47bebc1b0d1e29
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
---
# <a name="plan-for-skype-for-business-in-vdi-environments"></a>Planejar para o Skype for Business em ambientes VDI
 
Este tópico aborda considerações de planejamento para uso do Skype for Business durante a conexão a uma área de trabalho remota virtual. 
  
Um ambiente VDI (Virtual Desktop Infrastructure) é usado em algumas organizações onde questões de segurança e conformidade são especialmente sensíveis. Seus usuários trabalham em uma área de trabalho virtual com todos os arquivos e aplicativos da área de trabalho usando Serviços de Área de Trabalho Remota ou uma conexão remota similar. Usando o Skype for Business com completos de áudio e vídeo em uma conexão como essa requerem cargas intenso de áudio e vídeo de processamento no cliente hospedados em uma área de trabalho virtual. Software adicional de plug-in de VDI está disponível que libera o que o processamento de máquina de local do usuário final e reduz a carga da área de trabalho virtual.
  
Há três soluções disponíveis para o componente de plug-in de VDI, oferecido pela Microsoft, Citrix ou VMWare. Para implantações de novas, a Microsoft recomenda o uso da solução de pacote de otimização do Citrix HDX em tempo real ou o pacote de virtualização VMWare horizonte. O plug-in original do Lync VDI ainda é suportado para o restante do seu ciclo de vida.
  
- O **Lync VDI plug-in** foi desenvolvido para o Lync 2013 e é compatível com o Lync 2013 ou Skype para cliente 2015 corporativos em execução em uma área de trabalho virtual. Trata-se de um aplicativo autônomo que é instalado no computador local e permite o uso de dispositivos de áudio e vídeo locais com um cliente em uma área de trabalho virtual. O plug-in não exige um Skype para cliente Business seja instalado no computador local ou cliente fino, que deve ser executado sistemas operacionais Windows 7, Windows 8 ou Windows Server 2008. (Dispositivos cliente fino usando estes sistemas operacionais e suportada pela Microsoft incluem: Dell Wyse Z90D7, Dell Wyse R90L7, Dell Wyse X90m7, t610 HP e HP t5740e.) Esse plug-in ainda é suportado, mas não há atualizações futuras estão planejadas. Para ambientes virtuais baseados em Citrix, recomenda-se a utilização do Citrix RealTime Optimization Pack.
    
- O **Pacote de otimização de tempo real do Citrix** aproveita o Lync VDI plug-in e trabalha com o Lync 2013 ou Skype para clientes corporativos 2016 em uma área de trabalho virtual. Ele foi desenvolvido em parceria entre a Citrix e a Microsoft para aperfeiçoar o plug-in VDI original. Esse pacote pode ser instalado em clientes com sistemas operacionais Windows e não Windows (inclusive Windows 10, Mac e Linux). Ele consiste em dois componentes: o conector de tempo real (que é instalado na área de trabalho virtual) e o mecanismo de mídia em tempo real (que é instalado na máquina de local do usuário final). Esses dois componentes permitem que o computador local do usuário usar o Skype para cliente corporativos em execução na área de trabalho virtual com o / processamento V movido para o computador local. Para ambientes de área de trabalho virtual baseados em Citrix, recomenda-se a utilização do Citrix RealTime Optimization Pack, para o qual há mais suporte planejado.
    
- O **Pacote de virtualização VMWare horizonte** para Skype para empresas, desenvolvida em colaboração com VMWare, permite oferecer Skype para a empresa em uma área de trabalho virtual enquanto oferecem uma experiência de usuário excelente. O works solução utilizando o mecanismo de mídia no cliente para criar uma solução otimizada, com o ponto de extremidade do cliente fornecendo mídia descarregamento de recursos para chamadas de áudio e vídeos. Essa solução que pode oferecer áudio e vídeo tanto diretamente entre os pontos de extremidade para colaboração individuais ou descarregamento de para uma central multiponto unidade de controle (MCU) para chamadas de conferência com vários participantes ou reuniões.
    
> [!NOTE]
> O Skype para clientes de 2016 ou 2015 básica de negócios não são suportados com o pacote de otimização do Citrix HDX em tempo real ou o pacote de virtualização VMWare horizonte. 
  
## <a name="citrix-hdx-realtime-optimization-pack"></a>Citrix HDX RealTime Optimization Pack
<a name="Citrix_RT"> </a>

Plugin de ambiente de VDI da Citrix (um recurso do XenApp e XenDesktop) é compatível com o Lync 2013 e Skype para negócios 2015 2016 (total de clientes usando qualquer clique para executar o instalador ou instaladores MSI lançados após janeiro de 2017 PU) os clientes e instalados em um servidor virtual área de trabalho. Seu funcionamento geral baseia-se no Microsoft Lync VDI plug-in, mas funciona em uma variedade maior de sistemas operacionais de cliente, incluindo 10 do Windows, Macintosh e Linux.
  
Uma lista completa dos recursos e tecnologias suportadas pode ser encontrada no site da Citrix em [Fornecendo o Microsoft Skype para negócios XenApp e XenDesktop usuários](https://www.citrix.com/content/dam/citrix/en_us/documents/products-solutions/delivering-microsoft-lync-to-xenapp-and-xendesktop-users.pdf).
  
Confira os seguintes links para obter mais informações:
  
- Citrix [HDX em tempo real otimização Pack 2.1](https://docs.citrix.com/en-us/hdx-optimization/2-1.mdl)
    
- [Visão geral técnica](https://docs.citrix.com/en-us/hdx-optimization/2-1/about.mdl)
    
- [CTX200279 Skype para suporte ao recurso de negócios](https://support.citrix.com/article/CTX200279)
    
## <a name="vmware-horizon-virtualization-pack"></a>Pacote de virtualização VMWare horizonte
<a name="Citrix_RT"> </a>

Solução de ambiente de VDI da VMWare é compatível com Skype para negócios 2015 e 2016 clientes completos instalados em uma área de trabalho virtual. Seu funcionamento geral baseia-se no Microsoft Lync VDI plug-in, mas funciona em uma variedade maior de sistemas operacionais de cliente, incluindo 10 do Windows, Macintosh e Linux. 
  
Uma discussão completa dos recursos e tecnologias suportadas pode ser encontrada no site da VMWare nos seguintes links:
  
- [O que há de novo no VMware horizonte 7.4 &amp; horizonte cliente 4.7](https://blogs.vmware.com/euc/2018/01/vmware-horizon-7-4-horizon-client-4-7-whats-new.mdl)
    
- [Pacote de virtualização do horizonte para Skype para negócios](https://www.vmware.com/products/horizon/skype-for-business.mdl)
    
- [Microsoft Skype for Business com VMWare horizonte](https://www.vmware.com/content/dam/digitalmarketing/vmware/en/pdf/products/horizon/vmware-skype-for-business-solution-brief.pdf)
    
## <a name="microsofts-lync-vdi-plug-in"></a>Plug-in VDI do Microsoft Lync
<a name="Citrix_RT"> </a>

Com a solução de plug-in do Microsoft Lync VDI, o usuário deve estar em um computador com Windows ou de um cliente fino e ter o plug-in Lync VDI da Microsoft instalado para manipular fluxos de áudio/vídeo do cliente na área de trabalho virtual. O usuário deve:
  
1. Conectar um dispositivo de áudio/vídeo (como um fone de ouvido com microfone ou uma câmera) a um computador local.
    
2. Conecte-se a um desktop remoto virtual com um Lync 2013 ou Skype para 2015 de negócios do cliente.
    
3. Insira as credenciais para Skype para negócios na área de trabalho virtual.
    
4. Digite novamente as credenciais do usuário para estabelecer uma conexão com o Lync VDI plug-in no computador local do Windows ou cliente fino.
    
Depois que uma conexão é estabelecida, o usuário está pronto para fazer e receber chamadas de áudio e vídeo. O tráfego na rede e a carga na área de trabalho virtual são minimizados, pois o computador local faz o processamento de áudio e vídeo.
  
Plug-in Lync VDI do Microsoft é suportado somente em determinados sistemas operacionais do Windows e suporta apenas o Lync 2013 ou Skype para clientes corporativos 2015. Consulte [Tecnologias de virtualização suportadas e limitações conhecidas](vdi-environments.md#Supported_virt) para ver mais detalhes sobre as tecnologias compatíveis e as limitações.
  
Confira os seguintes links para obter mais informações:
  
- [Tecnologias de virtualização suportadas e limitações conhecidas](vdi-environments.md#Supported_virt)
    
- [Pré-requisitos do plug-in VDI do Lync](vdi-environments.md#VDI_prereq)
    
- [Implantar o Lync VDI plug-in com Skype para Business Server 2015](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)
    
- Artigo do Centro de dados de conhecimento do Citrix [CTX138408](https://support.citrix.com/article/CTX138408)
    
O Microsoft VDI plugin está disponível no [Microsoft Lync 2013 de VDI plugin (32 bits)](https://www.microsoft.com/en-us/download/details.aspx?id=35457) ou o [plug-in VDI do Microsoft Lync 2013 (64 bits)](https://www.microsoft.com/en-us/download/details.aspx?id=35454). Esse plug-in é compatível com o Skype para negócios 2015 cliente, apesar do nome.
  
### <a name="supported-virtualization-technologies-and-known-limitations"></a>Tecnologias de virtualização suportadas e limitações conhecidas
<a name="Supported_virt"> </a>

Permite que o plug-in Lync VDI, áudio e vídeo de chamar para as tecnologias de virtualização suportados. Em conformidade com as regulamentações de telefonia padrão, o suporte para E911 também está incluído. As seções a seguir descrevem as tecnologias de virtualização que são compatíveis com o Lync VDI plug-in e as limitações do recurso conhecido.
  
#### <a name="support-for-virtualization-technologies"></a>Suporte para Tecnologias de Virtualização

O plug-in Lync VDI oferece suporte a área de trabalho completa sessões remotas no cenário com área de trabalho virtual pessoal, mas não no cenário de sessão da área de trabalho remota. Esses cenários podem ser descritos da seguinte forma:
  
- **Com suporte: áreas de trabalho virtuais personalizadas ou VDI (Virtual Desktop Infrastructure).** Neste cenário, cada usuário faz logon em uma área de trabalho virtual personalizável e pode salvar arquivos na área de trabalho que persiste entre as sessões. Microsoft Remote Desktop Services e o modo de exibição do VMware horizonte são implementações de exemplo que foram testadas para uso com o Skype para negócios 2015. Outras implementações em processo de validação incluem o Citrix XenDesktop. Para obter informações sobre ambientes de VDI específica do fornecedor e o hardware de cliente que foram testados pela Microsoft, consulte [infraestrutura qualificados do Microsoft Lync](https://go.microsoft.com/fwlink/?LinkID=313435).
    
- **Sem suporte: sessões da área de trabalho remota.** Neste cenário, cada usuário faz logon em uma sessão da área de trabalho virtual genérica que não pode ser personalizada. Exemplos incluem sessões de área de trabalho remota (RDSH) Microsoft e Citrix XenApp combinada com Citrix receptor.
    
O plug-in Lync VDI não oferece suporte a outras tecnologias de virtualização, como a virtualização de aplicativo, que permite o uso de um aplicativo sem exigir a instalação do aplicativo completo localmente. Exemplos de implementações incluem o Citrix XenApp e a Microsoft Application Virtualization (App-V). Aplicação de streaming, comunicação remota de aplicativos e modelos de virtualização mistos (por exemplo, comunicação remota de aplicativos em toda a área de trabalho remota) não são suportados.
  
O plug-in Lync VDI foi desenvolvido para usar APIs independente de plataforma denominados canais de Virtual dinâmico (DVCs). Para cenários que não têm suporte explicitamente, consulte as instruções de suporte do provedor sobre soluções de VDI.
  
#### <a name="lync-vdi-plug-in-prerequisites"></a>Pré-requisitos do plug-in Lync VDI
<a name="VDI_prereq"> </a>

Em um ambiente VDI, as máquinas virtuais e o computador local do usuário devem atender os requisitos destacados nesta seção.
  
> [!NOTE]
>  Seu provedor de soluções de virtualização pode fornecer detalhes de como instalar e implantar o ambiente. Para obter informações gerais sobre como implantar um ambiente virtualizado com base no Hyper-V e os serviços de área de trabalho remota, consulte os seguintes artigos na TechNet Library Microsoft: [Hyper-V](https://go.microsoft.com/fwlink/p/?linkid=247514), [Os serviços de área de trabalho remota no Windows Server 2008 R2](https://go.microsoft.com/fwlink/p/?linkid=247513) 
  
Máquinas virtuais deve ser configuradas com Windows 8, Windows 7 ou Windows Server 2008 R2 com os service packs mais recentes.
  
Computador local do usuário deve atender aos seguintes requisitos:
  
- O usuário deve ser hospedado em Skype para Business Server 2015 ou o Lync Server 2013.
    
- O computador local deve estar executando o Windows Embedded Standard 7 com SP1, Windows 7 com SP1 ou Windows 8.
    
- Se você estiver usando os serviços de área de trabalho remota, escolha o 32 bits ou 64 bits Lync VDI plug-in para coincidir com o sistema operacional do computador local. Não é obrigatório que o computador local e a máquina virtual tenham sistemas operacionais de 32 bits ou de 64 bits. Se você estiver usando outra plataforma ou solução de virtualização, consulte os requisitos do provedor.
    
- O computador local deve estar executando a [versão mais recente do cliente de desktop remoto](https://go.microsoft.com/fwlink/p/?LinkId=268032). Instale as últimas atualizações do cliente de Serviços de Área de Trabalho Remota da Microsoft ou o software cliente de área de trabalho remota mais recente do seu provedor de soluções de virtualização. 
    
- No computador local, as configurações do cliente de área de trabalho remota devem ser definidas para que o áudio seja reproduzido no computador local e a gravação remota seja desabilitada. Para definir essas configurações para a Conexão de área de trabalho remota no Windows, consulte a próxima seção, "para definir as configurações de Conexão de área de trabalho remota." 
    
O Microsoft VDI plugin está disponível no [Microsoft Lync 2013 de VDI plugin (32 bits)](https://www.microsoft.com/en-us/download/details.aspx?id=35457) ou o [plug-in VDI do Microsoft Lync 2013 (64 bits)](https://www.microsoft.com/en-us/download/details.aspx?id=35454).
  
#### <a name="known-feature-limitations"></a>Limitações conhecidas dos recursos
<a name="VDI_prereq"> </a>

A seguir há algumas limitações conhecida quando você usa o Skype para negócios 2015 cliente em um ambiente de VDI:
  
Não há suporte limitado para recursos de delegação de chamadas e anonimato de agente do grupo de resposta.
  
Não há suporte aos seguintes recursos:
  
- Páginas de ajuste de dispositivo de áudio integrado e dispositivo de vídeo
    
- Vídeo com modo de exibição múltipla.
    
- Gravação de conversas.
    
- Participar de reuniões anônimo (isto é, participar Skype para reuniões de negócios hospedadas por uma organização que não esteja federadas à sua organização).
    
- Usando o Lync VDI plug-in, juntamente com um dispositivo do Lync Phone Edition.
    
- Continuidade de chamadas em caso de indisponibilidade da rede.
    
- Toques personalizados e recursos de música em espera.
    
Não há suporte para o Lync VDI plug-in em um ambiente do Office 365.
  
> [!NOTE]
> O Citrix RealTime Optimization Pack dá suporte ao Office 365. Baseado em Citrix ambientes virtuais, examine a documentação de [Visão geral técnica](https://docs.citrix.com/en-us/hdx-optimization/2-0/hdx-realtime-optimization-pack-about.mdl) do Citrix para a lista de recursos com suporte e versões.
  
## <a name="see-also"></a>Ver também
<a name="Citrix_RT"> </a>

[Implantar o Lync VDI plug-in com Skype para Business Server 2015](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)

