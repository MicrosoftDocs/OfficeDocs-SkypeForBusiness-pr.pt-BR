---
title: Editar Expansor de Configurações de Borda para Lync Server 2010
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 74a66817-7092-4b2f-a2af-bc1a2c9e5fed
description: 'Você pode editar as configurações para o servidor de borda ou pool de borda, definindo as seguintes propriedades:'
ms.openlocfilehash: a4ad88aa6ff565ac7c1ebb5134d476d34625418f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32203127"
---
# <a name="edit-edge-settings-expander-for-lync-server-2010"></a><span data-ttu-id="91415-103">Editar Expansor de Configurações de Borda para Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="91415-103">Edit Edge Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="91415-104">Você pode editar as configurações para o servidor de borda ou pool de borda, definindo as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="91415-104">You edit the settings for the Edge Server or Edge pool by configuring the following properties:</span></span> 
  
 <span data-ttu-id="91415-105">**Geral**</span><span class="sxs-lookup"><span data-stu-id="91415-105">**General**</span></span>
  
- <span data-ttu-id="91415-106">**FQDN do pool interno**: O nome de domínio totalmente qualificado do pool interno é a identidade do servidor de borda ou pool de borda conforme definido no registro de host (A ou AAAA para IPv6) domínio nomes DNS (sistema).</span><span class="sxs-lookup"><span data-stu-id="91415-106">**Internal pool FQDN**: The internal pool fully qualified domain name is the identity of the Edge Server or Edge pool as defined in the domain name system (DNS) host (A or AAAA for IPv6) record.</span></span>
    
- <span data-ttu-id="91415-107">Selecione **Habilitar federação para este pool de borda (porta 5061)** se você deseja habilitar o servidor de borda ou pool de borda para federação com outros parceiros de protocolo de iniciação de sessão.</span><span class="sxs-lookup"><span data-stu-id="91415-107">Select **Enable federation for this Edge pool (port 5061)** if you want to enable the Edge Server or Edge pool for federation with other session initiation protocol partners.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="91415-108">Você só pode definir um servidor de borda ou pool de borda ativamente para federação.</span><span class="sxs-lookup"><span data-stu-id="91415-108">You can only define one Edge Server or Edge pool actively for federation.</span></span> <span data-ttu-id="91415-109">A configuração mostrada na captura de tela associada indica que outro pool do servidor de borda ou borda já está configurado para federação.</span><span class="sxs-lookup"><span data-stu-id="91415-109">The configuration shown in the associated screen shot indicates that another Edge Server or Edge pool is already configured for federation.</span></span> <span data-ttu-id="91415-110">O registro SRV de DNS para federação (_sipfederationtls._tcp.\< nome de domínio externo\>) apontará para o servidor de borda ou pool de borda para federação.</span><span class="sxs-lookup"><span data-stu-id="91415-110">The external DNS SRV record for federation (_sipfederationtls._tcp.\<external domain name\>) will point to the Edge Server or Edge pool for federation.</span></span> 
  
- <span data-ttu-id="91415-111">A **Porta de replicação de configuração interna (HTTPS)**, por padrão, a porta TCP 4443, é a porta que o local (ou seja, local para os servidores de borda) cópia do repositório de gerenciamento Central está sendo replicada.</span><span class="sxs-lookup"><span data-stu-id="91415-111">The **Internal Configuration Replication Port (HTTPS)**, by default at TCP port 4443, is the port that the local (that is, local to the Edge Servers) copy of the Central Management store is replicated over.</span></span> <span data-ttu-id="91415-112">A cópia local do repositório de gerenciamento Central está no banco de dados **RTCLOCAL** no SQL Server em cada computador.</span><span class="sxs-lookup"><span data-stu-id="91415-112">The local copy of the Central Management store is in the **RTCLOCAL** database in the SQL Server on each computer.</span></span> <span data-ttu-id="91415-113">A replicação é unidirecional, iniciado a partir do servidor de gerenciamento Central (ou o pool de Front-End ou de servidor Front-End que detém a função de servidor de gerenciamento Central) para os servidores de borda e é uma porta da interface interna.</span><span class="sxs-lookup"><span data-stu-id="91415-113">The replication is one-way, initiated from the Central Management Server (or, the Front End Server or Front End pool that holds the Central Management Server role) to the Edge Servers and is an internal interface port.</span></span>
    
  <span data-ttu-id="91415-114">**Seleção do próximo salto**</span><span class="sxs-lookup"><span data-stu-id="91415-114">**Next hop selection**</span></span>
  
- <span data-ttu-id="91415-115">Selecione na lista de seu **pool de próximo salto**.</span><span class="sxs-lookup"><span data-stu-id="91415-115">Select for the list your **Next hop pool**.</span></span> <span data-ttu-id="91415-116">Você define um diretor, pool de diretor, pool de Front-End ou de servidor Front-End para assumir essa função.</span><span class="sxs-lookup"><span data-stu-id="91415-116">You define either a Director, Director pool, Front End Server or Front End pool to assume this role.</span></span> <span data-ttu-id="91415-117">O pool de próximo salto é o servidor ou pool de servidores que aceitará mensagens de SIP de entrada do servidor de borda ou interface interna do pool de borda e enviar saída SIP para a interface interna de borda.</span><span class="sxs-lookup"><span data-stu-id="91415-117">The next hop pool is the server or server pool that will accept inbound SIP messages from the Edge Server or Edge pool internal interface and send outbound SIP to the Edge internal interface.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="91415-118">O diretor é uma função opcional e se você decidir não implantar os diretores, os servidores Front-End (computador único ou pool) assumirá a função Diretor.</span><span class="sxs-lookup"><span data-stu-id="91415-118">The Director is an optional role and if you decide not to deploy Directors, the Front End Servers (single computer or pool) will assume the Director role.</span></span> 
  
  <span data-ttu-id="91415-119">**Configurações externas**</span><span class="sxs-lookup"><span data-stu-id="91415-119">**External settings**</span></span>
  
<span data-ttu-id="91415-120">Esta seção das propriedades permite editar propriedades para as configurações externas do servidor de borda ou pool de borda.</span><span class="sxs-lookup"><span data-stu-id="91415-120">This section of the properties allows you to edit properties for the external settings of the Edge Server or Edge pool.</span></span> <span data-ttu-id="91415-121">Estas propriedades estão disponíveis para edição:</span><span class="sxs-lookup"><span data-stu-id="91415-121">The following properties are available to edit:</span></span>
  
- <span data-ttu-id="91415-122">Selecione o **FQDN de habilitar separado e endereço IP para Webconferência e A / V** nomes de caixa de seleção se você desejar atribuir diferentes endereços IP e domínio totalmente qualificado para cada serviço de servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="91415-122">Select the **Enable separate FQDN and IP address for web conferencing and A/V** check box if you want to assign distinct IP addresses and fully qualified domain names to each Edge Server service.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="91415-123">Se você optar por não marque a caixa de seleção, você deve usar portas separadas para cada serviço de borda.</span><span class="sxs-lookup"><span data-stu-id="91415-123">If you choose to not select the check box, you must use separate ports for each Edge service.</span></span> <span data-ttu-id="91415-124">Cada serviço de borda compartilharão o FQDN definido para o serviço de borda de acesso e, portanto, usará o mesmo endereço IP.</span><span class="sxs-lookup"><span data-stu-id="91415-124">Each Edge service will share the FQDN defined for the Access Edge service, and will therefore use the same IP address.</span></span> <span data-ttu-id="91415-125">Cada serviço de borda deve ser identificado exclusivamente um endereço IP distinto e mesma porta, ou o mesmo endereço IP e os valores de porta exclusivo.</span><span class="sxs-lookup"><span data-stu-id="91415-125">Each Edge service must be uniquely identified by either a distinct IP address and same port, or the same IP address and unique port values.</span></span> 
  
- <span data-ttu-id="91415-126">Selecione **uma / serviço de borda V é habilitado para NAT** se você deseja configurar A usar um endereço privado ou outro endereço que ficará oculta atrás de um dispositivo NAT (conversão) de endereço de rede do serviço de borda V /.</span><span class="sxs-lookup"><span data-stu-id="91415-126">Select **A/V Edge service is NAT enabled** if you want to configure the A/V Edge service to use a private address or other address that will be hidden behind a network address translation (NAT) device.</span></span>
    
- <span data-ttu-id="91415-127">Para editar o **serviço de borda de acesso**, definir o **FQDN do Pool** para o serviço de borda de acesso conforme definido no DNS pelo host (A e AAAA se IPv6 for usado) um valor de porta e de registros</span><span class="sxs-lookup"><span data-stu-id="91415-127">To edit the **Access Edge service**, you define the **Pool FQDN** for the Access Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
- <span data-ttu-id="91415-128">Para editar o **serviço de borda de webconferência**, definir um **FQDN do Pool** para o serviço de borda de webconferência conforme definido no DNS pelo host (A e AAAA se IPv6 for usado) um valor de porta e de registros</span><span class="sxs-lookup"><span data-stu-id="91415-128">To edit the **Web Conferencing Edge service**, you define a **Pool FQDN** for the Web Conferencing Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
- <span data-ttu-id="91415-129">Para editar o **uma / serviço de borda V**, você define um **FQDN do Pool** para A serviço de borda V conforme definido no DNS pelo host (A e AAAA se IPv6 for usado) / registros e um valor de porta</span><span class="sxs-lookup"><span data-stu-id="91415-129">To edit the **A/V Edge service**, you define a **Pool FQDN** for the A/V Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="91415-130">Se você tiver selecionado o **FQDN de habilitar separado e endereço IP para Webconferência e A / V** caixa de seleção, apenas o serviço de borda de acesso FQDN do Pool estarão disponível para edição.</span><span class="sxs-lookup"><span data-stu-id="91415-130">If you have selected the **Enable separate FQDN and IP address for web conferencing and A/V** check box, only the Access Edge service Pool FQDN will be available for editing.</span></span> <span data-ttu-id="91415-131">Atribua portas distintas para cada um dos três serviços de borda.</span><span class="sxs-lookup"><span data-stu-id="91415-131">Assign distinct ports for each of the three Edge services.</span></span>
  
  <span data-ttu-id="91415-132">**OK** Aceita e confirma as alterações na caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="91415-132">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="91415-133">**Cancelar** Descarta as alterações e fecha a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="91415-133">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="91415-134">**Ajuda** Exibe essa tela de ajuda.</span><span class="sxs-lookup"><span data-stu-id="91415-134">**Help** Displays this help screen.</span></span>
  

