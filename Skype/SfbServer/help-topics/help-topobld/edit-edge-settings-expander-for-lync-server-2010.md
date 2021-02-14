---
title: Editar Expansor de Configurações de Borda para Lync Server 2010
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 74a66817-7092-4b2f-a2af-bc1a2c9e5fed
description: 'Edite as configurações para o Servidor de Borda ou pool de Borda definindo as seguintes propriedades:'
ms.openlocfilehash: f77eb71948bbbe6d2fe3e24b400d29e3bf5fd5a5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803291"
---
# <a name="edit-edge-settings-expander-for-lync-server-2010"></a><span data-ttu-id="b5817-103">Editar Expansor de Configurações de Borda para Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="b5817-103">Edit Edge Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="b5817-104">Edite as configurações para o Servidor de Borda ou pool de Borda definindo as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="b5817-104">You edit the settings for the Edge Server or Edge pool by configuring the following properties:</span></span> 
  
 <span data-ttu-id="b5817-105">**Geral**</span><span class="sxs-lookup"><span data-stu-id="b5817-105">**General**</span></span>
  
- <span data-ttu-id="b5817-106">**FQDN** do pool interno: o nome de domínio totalmente qualificado do pool interno é a identidade do Servidor de Borda ou pool de Borda, conforme definido no registro de host do sistema de nomes de domínio (DNS) (A ou AAAA para IPv6).</span><span class="sxs-lookup"><span data-stu-id="b5817-106">**Internal pool FQDN**: The internal pool fully qualified domain name is the identity of the Edge Server or Edge pool as defined in the domain name system (DNS) host (A or AAAA for IPv6) record.</span></span>
    
- <span data-ttu-id="b5817-107">Selecione Habilitar federação para este pool de Borda **(porta 5061)** se quiser habilitar o Servidor de Borda ou o pool de Borda para federação com outros parceiros de protocolo de iniciação de sessão.</span><span class="sxs-lookup"><span data-stu-id="b5817-107">Select **Enable federation for this Edge pool (port 5061)** if you want to enable the Edge Server or Edge pool for federation with other session initiation protocol partners.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="b5817-108">Você só pode definir um Servidor de Borda ou pool de Borda ativamente para federação.</span><span class="sxs-lookup"><span data-stu-id="b5817-108">You can only define one Edge Server or Edge pool actively for federation.</span></span> <span data-ttu-id="b5817-109">A configuração mostrada na captura de tela associada indica que outro Servidor de Borda ou pool de Borda já está configurado para federação.</span><span class="sxs-lookup"><span data-stu-id="b5817-109">The configuration shown in the associated screen shot indicates that another Edge Server or Edge pool is already configured for federation.</span></span> <span data-ttu-id="b5817-110">O registro SRV dns externo para federação (_sipfederationtls._tcp. ) apontará para o Servidor de Borda ou pool de Borda \<external domain name\> para federação.</span><span class="sxs-lookup"><span data-stu-id="b5817-110">The external DNS SRV record for federation (_sipfederationtls._tcp.\<external domain name\>) will point to the Edge Server or Edge pool for federation.</span></span> 
  
- <span data-ttu-id="b5817-111">A Porta de Replicação de Configuração Interna **(HTTPS),** por padrão na porta TCP 4443, é a porta pela que a cópia local (isto é, local para os Servidores de Borda) do armazenamento de Gerenciamento Central é replicada.</span><span class="sxs-lookup"><span data-stu-id="b5817-111">The **Internal Configuration Replication Port (HTTPS)**, by default at TCP port 4443, is the port that the local (that is, local to the Edge Servers) copy of the Central Management store is replicated over.</span></span> <span data-ttu-id="b5817-112">A cópia local do armazenamento de Gerenciamento Central está no banco de **dados RTCLOCAL** no SQL Server em cada computador.</span><span class="sxs-lookup"><span data-stu-id="b5817-112">The local copy of the Central Management store is in the **RTCLOCAL** database in the SQL Server on each computer.</span></span> <span data-ttu-id="b5817-113">A replicação é única, iniciada a partir do Servidor de Gerenciamento Central (ou, o Servidor de Front End ou pool de Front-End que mantém a função de Servidor de Gerenciamento Central) para os Servidores de Borda e é uma porta de interface interna.</span><span class="sxs-lookup"><span data-stu-id="b5817-113">The replication is one-way, initiated from the Central Management Server (or, the Front End Server or Front End pool that holds the Central Management Server role) to the Edge Servers and is an internal interface port.</span></span>
    
  <span data-ttu-id="b5817-114">**Seleção de próximo salto**</span><span class="sxs-lookup"><span data-stu-id="b5817-114">**Next hop selection**</span></span>
  
- <span data-ttu-id="b5817-115">Selecione para lista seu **Pool de próximo salto**.</span><span class="sxs-lookup"><span data-stu-id="b5817-115">Select for the list your **Next hop pool**.</span></span> <span data-ttu-id="b5817-116">Você define um Diretor, pool de Diretores, Servidor front-end ou pool de front-end para assumir essa função.</span><span class="sxs-lookup"><span data-stu-id="b5817-116">You define either a Director, Director pool, Front End Server or Front End pool to assume this role.</span></span> <span data-ttu-id="b5817-117">O pool de próximo salto é o servidor ou pool de servidores que aceitará mensagens SIP de entrada do Servidor de Borda ou da interface interna do pool de Borda e enviará SIP de saída para a interface interna da Borda.</span><span class="sxs-lookup"><span data-stu-id="b5817-117">The next hop pool is the server or server pool that will accept inbound SIP messages from the Edge Server or Edge pool internal interface and send outbound SIP to the Edge internal interface.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b5817-118">O Diretor é uma função opcional e, se você decidir não implantar Diretores, os Servidores Front End (computador único ou pool) assumirão a função de Diretor.</span><span class="sxs-lookup"><span data-stu-id="b5817-118">The Director is an optional role and if you decide not to deploy Directors, the Front End Servers (single computer or pool) will assume the Director role.</span></span> 
  
  <span data-ttu-id="b5817-119">**Configurações externas**</span><span class="sxs-lookup"><span data-stu-id="b5817-119">**External settings**</span></span>
  
<span data-ttu-id="b5817-120">Esta seção das propriedades permite que você edite propriedades para as configurações externas do Servidor de Borda ou pool de Borda.</span><span class="sxs-lookup"><span data-stu-id="b5817-120">This section of the properties allows you to edit properties for the external settings of the Edge Server or Edge pool.</span></span> <span data-ttu-id="b5817-121">As propriedades a seguir estão disponíveis para edição:</span><span class="sxs-lookup"><span data-stu-id="b5817-121">The following properties are available to edit:</span></span>
  
- <span data-ttu-id="b5817-122">Marque a caixa de seleção Habilitar **FQDN** e endereço IP separados para webconferência e A/V se quiser atribuir endereços IP distintos e nomes de domínio totalmente qualificados a cada serviço de Servidor de Borda.</span><span class="sxs-lookup"><span data-stu-id="b5817-122">Select the **Enable separate FQDN and IP address for web conferencing and A/V** check box if you want to assign distinct IP addresses and fully qualified domain names to each Edge Server service.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b5817-123">Se você escolher não marcar a caixa de seleção, deverá usar portas separadas para cada serviço de Borda.</span><span class="sxs-lookup"><span data-stu-id="b5817-123">If you choose to not select the check box, you must use separate ports for each Edge service.</span></span> <span data-ttu-id="b5817-124">Cada serviço de Borda compartilhará o FQDN definido para o serviço de Borda de Acesso e, portanto, usará o mesmo endereço IP.</span><span class="sxs-lookup"><span data-stu-id="b5817-124">Each Edge service will share the FQDN defined for the Access Edge service, and will therefore use the same IP address.</span></span> <span data-ttu-id="b5817-125">Cada serviço de Borda precisa ser identificado exclusivamente por um endereço IP distinto e pela mesma porta, ou o mesmo endereço IP e valores de porta exclusivos.</span><span class="sxs-lookup"><span data-stu-id="b5817-125">Each Edge service must be uniquely identified by either a distinct IP address and same port, or the same IP address and unique port values.</span></span> 
  
- <span data-ttu-id="b5817-126">Selecione o serviço de Borda **A/V** como NAT habilitado se você quiser configurar o serviço de Borda A/V para usar um endereço privado ou outro endereço que ficará oculto atrás de um dispositivo NAT (conversão de endereço de rede).</span><span class="sxs-lookup"><span data-stu-id="b5817-126">Select **A/V Edge service is NAT enabled** if you want to configure the A/V Edge service to use a private address or other address that will be hidden behind a network address translation (NAT) device.</span></span>
    
- <span data-ttu-id="b5817-127">Para editar o serviço de Borda de **Acesso,** defina o **FQDN** do Pool para o serviço de Borda de Acesso conforme definido no DNS pelos registros de host (A e AAAA se IPv6 for usado) e um valor de porta</span><span class="sxs-lookup"><span data-stu-id="b5817-127">To edit the **Access Edge service**, you define the **Pool FQDN** for the Access Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
- <span data-ttu-id="b5817-128">Para editar o serviço de Borda de Webconferência, defina um **FQDN** de Pool para o serviço de Borda de Webconferência conforme definido no DNS pelos registros de host (A e AAAA se IPv6 for usado) e um valor de porta</span><span class="sxs-lookup"><span data-stu-id="b5817-128">To edit the **Web Conferencing Edge service**, you define a **Pool FQDN** for the Web Conferencing Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
- <span data-ttu-id="b5817-129">Para editar o serviço de Borda **A/V,** defina um **FQDN** de Pool para o serviço de Borda A/V conforme definido no DNS pelos registros de host (A e AAAA se IPv6 for usado) e um valor de porta</span><span class="sxs-lookup"><span data-stu-id="b5817-129">To edit the **A/V Edge service**, you define a **Pool FQDN** for the A/V Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="b5817-130">Se você tiver marcado a caixa de seleção Habilitar FQDN e endereço IP separados para webconferência e **A/V,** somente o FQDN do Pool de Serviços de Borda de Acesso estará disponível para edição.</span><span class="sxs-lookup"><span data-stu-id="b5817-130">If you have selected the **Enable separate FQDN and IP address for web conferencing and A/V** check box, only the Access Edge service Pool FQDN will be available for editing.</span></span> <span data-ttu-id="b5817-131">Atribua portas distintas para cada um dos três serviços de Borda.</span><span class="sxs-lookup"><span data-stu-id="b5817-131">Assign distinct ports for each of the three Edge services.</span></span>
  
  <span data-ttu-id="b5817-132">**OK** aceita e confirma as alterações na caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="b5817-132">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="b5817-133">**Cancelar** descarta as alterações e fecha a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="b5817-133">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="b5817-134">**Ajuda** exibe essa tela de ajuda.</span><span class="sxs-lookup"><span data-stu-id="b5817-134">**Help** Displays this help screen.</span></span>
  

