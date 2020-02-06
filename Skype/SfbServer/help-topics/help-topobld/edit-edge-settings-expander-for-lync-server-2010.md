---
title: Editar Expansor de Configurações de Borda para Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.EdgeSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 74a66817-7092-4b2f-a2af-bc1a2c9e5fed
description: 'Edite as configurações do servidor de borda ou do pool de bordas configurando as seguintes propriedades:'
ms.openlocfilehash: f483f87ad6c7ba6fa8cfc89e0b5d11899a68119a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820003"
---
# <a name="edit-edge-settings-expander-for-lync-server-2010"></a><span data-ttu-id="ac1e9-103">Editar Expansor de Configurações de Borda para Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="ac1e9-103">Edit Edge Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="ac1e9-104">Edite as configurações do servidor de borda ou do pool de bordas configurando as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="ac1e9-104">You edit the settings for the Edge Server or Edge pool by configuring the following properties:</span></span> 
  
 <span data-ttu-id="ac1e9-105">**Geral**</span><span class="sxs-lookup"><span data-stu-id="ac1e9-105">**General**</span></span>
  
- <span data-ttu-id="ac1e9-106">**FQDN do pool interno**: o nome de domínio totalmente qualificado do pool interno é a identidade do servidor de borda ou o pool de bordas, conforme definido no registro do host de sistema de nomes de domínio (DNS) do host (A ou aaaa para IPv6).</span><span class="sxs-lookup"><span data-stu-id="ac1e9-106">**Internal pool FQDN**: The internal pool fully qualified domain name is the identity of the Edge Server or Edge pool as defined in the domain name system (DNS) host (A or AAAA for IPv6) record.</span></span>
    
- <span data-ttu-id="ac1e9-107">Selecione **habilitar Federação para este pool de bordas (porta 5061)** se você quiser habilitar o servidor de borda ou o pool de bordas para federação com outros parceiros de protocolo de início de sessão.</span><span class="sxs-lookup"><span data-stu-id="ac1e9-107">Select **Enable federation for this Edge pool (port 5061)** if you want to enable the Edge Server or Edge pool for federation with other session initiation protocol partners.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="ac1e9-108">Você só pode definir um servidor de borda ou um pool de bordas ativamente para Federação.</span><span class="sxs-lookup"><span data-stu-id="ac1e9-108">You can only define one Edge Server or Edge pool actively for federation.</span></span> <span data-ttu-id="ac1e9-109">A configuração mostrada na captura de tela associada indica que outro servidor de borda ou um pool de bordas já está configurado para Federação.</span><span class="sxs-lookup"><span data-stu-id="ac1e9-109">The configuration shown in the associated screen shot indicates that another Edge Server or Edge pool is already configured for federation.</span></span> <span data-ttu-id="ac1e9-110">O registro SRV DNS externo para Federação (_sipfederationtls. _tcp.\< nome\>do domínio externo) apontará para o servidor de borda ou o pool de bordas para Federação.</span><span class="sxs-lookup"><span data-stu-id="ac1e9-110">The external DNS SRV record for federation (_sipfederationtls._tcp.\<external domain name\>) will point to the Edge Server or Edge pool for federation.</span></span> 
  
- <span data-ttu-id="ac1e9-111">A **porta de replicação de configuração interna (https)**, por padrão, na porta TCP 4443, é a porta que a cópia local (ou seja, local para os servidores de extremidade) do repositório de gerenciamento central é replicada.</span><span class="sxs-lookup"><span data-stu-id="ac1e9-111">The **Internal Configuration Replication Port (HTTPS)**, by default at TCP port 4443, is the port that the local (that is, local to the Edge Servers) copy of the Central Management store is replicated over.</span></span> <span data-ttu-id="ac1e9-112">A cópia local do repositório de gerenciamento central está no banco de dados do **RTCLOCAL** no SQL Server em cada computador.</span><span class="sxs-lookup"><span data-stu-id="ac1e9-112">The local copy of the Central Management store is in the **RTCLOCAL** database in the SQL Server on each computer.</span></span> <span data-ttu-id="ac1e9-113">A replicação é unidirecional, iniciada a partir do servidor de gerenciamento central (ou, o servidor front-end ou o pool de front-ends que mantém a função de servidor central de gerenciamento) para os servidores de borda e é uma porta de interface interna.</span><span class="sxs-lookup"><span data-stu-id="ac1e9-113">The replication is one-way, initiated from the Central Management Server (or, the Front End Server or Front End pool that holds the Central Management Server role) to the Edge Servers and is an internal interface port.</span></span>
    
  <span data-ttu-id="ac1e9-114">**Seleção do próximo salto**</span><span class="sxs-lookup"><span data-stu-id="ac1e9-114">**Next hop selection**</span></span>
  
- <span data-ttu-id="ac1e9-115">Selecione para a lista do **próximo pool de saltos**.</span><span class="sxs-lookup"><span data-stu-id="ac1e9-115">Select for the list your **Next hop pool**.</span></span> <span data-ttu-id="ac1e9-116">Você define um director, um pool de directors, um servidor front-end ou um pool de front-end para assumir essa função.</span><span class="sxs-lookup"><span data-stu-id="ac1e9-116">You define either a Director, Director pool, Front End Server or Front End pool to assume this role.</span></span> <span data-ttu-id="ac1e9-117">O próximo pool de saltos é o servidor ou pool de servidores que aceitará mensagens SIP de entrada do servidor de borda ou da interface interna do pool de bordas e enviará o SIP de saída para a interface interna de Edge.</span><span class="sxs-lookup"><span data-stu-id="ac1e9-117">The next hop pool is the server or server pool that will accept inbound SIP messages from the Edge Server or Edge pool internal interface and send outbound SIP to the Edge internal interface.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ac1e9-118">O diretor é uma função opcional e, se você decidir não implantar diretores, os servidores front-end (computador ou pool único) assumirão a função de diretor.</span><span class="sxs-lookup"><span data-stu-id="ac1e9-118">The Director is an optional role and if you decide not to deploy Directors, the Front End Servers (single computer or pool) will assume the Director role.</span></span> 
  
  <span data-ttu-id="ac1e9-119">**Configurações externas**</span><span class="sxs-lookup"><span data-stu-id="ac1e9-119">**External settings**</span></span>
  
<span data-ttu-id="ac1e9-120">Esta seção das propriedades permite que você edite as propriedades das configurações externas do servidor de borda ou do pool de bordas.</span><span class="sxs-lookup"><span data-stu-id="ac1e9-120">This section of the properties allows you to edit properties for the external settings of the Edge Server or Edge pool.</span></span> <span data-ttu-id="ac1e9-121">Estas propriedades estão disponíveis para edição:</span><span class="sxs-lookup"><span data-stu-id="ac1e9-121">The following properties are available to edit:</span></span>
  
- <span data-ttu-id="ac1e9-122">Marque a caixa de seleção **habilitar FQDN e endereço IP separados para Webconferência e a/V,** se você quiser atribuir endereços IP distintos e nomes de domínio totalmente qualificados a cada serviço de servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="ac1e9-122">Select the **Enable separate FQDN and IP address for web conferencing and A/V** check box if you want to assign distinct IP addresses and fully qualified domain names to each Edge Server service.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ac1e9-123">Se você optar por não marcar a caixa de seleção, deverá usar portas separadas para cada serviço de borda.</span><span class="sxs-lookup"><span data-stu-id="ac1e9-123">If you choose to not select the check box, you must use separate ports for each Edge service.</span></span> <span data-ttu-id="ac1e9-124">Cada serviço de borda compartilhará o FQDN definido para o serviço de borda de acesso e, portanto, usará o mesmo endereço IP.</span><span class="sxs-lookup"><span data-stu-id="ac1e9-124">Each Edge service will share the FQDN defined for the Access Edge service, and will therefore use the same IP address.</span></span> <span data-ttu-id="ac1e9-125">Cada serviço de borda deve ser identificado exclusivamente por um endereço IP distinto e mesma porta, ou pelo mesmo endereço IP e valores de porta exclusivos.</span><span class="sxs-lookup"><span data-stu-id="ac1e9-125">Each Edge service must be uniquely identified by either a distinct IP address and same port, or the same IP address and unique port values.</span></span> 
  
- <span data-ttu-id="ac1e9-126">Selecione o **serviço de borda a/v está habilitado para NAT** se você quiser configurar o serviço de borda a/v para usar um endereço particular ou outro endereço que ficará oculto atrás de um dispositivo NAT (conversão de endereços de rede).</span><span class="sxs-lookup"><span data-stu-id="ac1e9-126">Select **A/V Edge service is NAT enabled** if you want to configure the A/V Edge service to use a private address or other address that will be hidden behind a network address translation (NAT) device.</span></span>
    
- <span data-ttu-id="ac1e9-127">Para editar o **serviço de borda de acesso**, defina o **FQDN do pool** para o serviço de borda de acesso conforme definido no DNS pelos registros host (A e AAAA se IPv6 são usados) e um valor de porta</span><span class="sxs-lookup"><span data-stu-id="ac1e9-127">To edit the **Access Edge service**, you define the **Pool FQDN** for the Access Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
- <span data-ttu-id="ac1e9-128">Para editar o **serviço de borda de Webconferência**, defina um **FQDN de pool** para o serviço de borda de webconferência, conforme definido no DNS, os registros host (a e AAAA se IPv6 são usados) e um valor de porta</span><span class="sxs-lookup"><span data-stu-id="ac1e9-128">To edit the **Web Conferencing Edge service**, you define a **Pool FQDN** for the Web Conferencing Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
- <span data-ttu-id="ac1e9-129">Para editar o **serviço de borda a/v**, você define um **FQDN de pool** para o serviço de borda a/v, conforme definido no DNS por registros host (A e AAAA se IPv6 são usados) e um valor de porta</span><span class="sxs-lookup"><span data-stu-id="ac1e9-129">To edit the **A/V Edge service**, you define a **Pool FQDN** for the A/V Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="ac1e9-130">Se você tiver marcado a caixa de seleção **habilitar FQDN e endereço IP separados para Webconferência e a/V** , somente o FQDN do pool de serviços de borda de acesso estará disponível para edição.</span><span class="sxs-lookup"><span data-stu-id="ac1e9-130">If you have selected the **Enable separate FQDN and IP address for web conferencing and A/V** check box, only the Access Edge service Pool FQDN will be available for editing.</span></span> <span data-ttu-id="ac1e9-131">Atribua portas distintas para cada um dos três serviços de borda.</span><span class="sxs-lookup"><span data-stu-id="ac1e9-131">Assign distinct ports for each of the three Edge services.</span></span>
  
  <span data-ttu-id="ac1e9-132">**OK** Aceita e confirma as alterações na caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="ac1e9-132">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="ac1e9-133">**Cancelar** Descarta as alterações e fecha a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="ac1e9-133">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="ac1e9-134">**Ajuda** Exibe essa tela de ajuda.</span><span class="sxs-lookup"><span data-stu-id="ac1e9-134">**Help** Displays this help screen.</span></span>
  

