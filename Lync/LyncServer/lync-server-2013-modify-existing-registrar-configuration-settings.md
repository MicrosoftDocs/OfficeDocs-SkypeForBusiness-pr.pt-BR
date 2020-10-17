---
title: 'Lync Server 2013: Modificar definições de configuração do registrador existente'
description: 'Lync Server 2013: Modificar definições de configuração do registrador existente.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify existing Registrar configuration settings
ms:assetid: a8931511-3e66-49ed-a3ec-03bcd61ce1f0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182566(v=OCS.15)
ms:contentKeyID: 48185095
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a4a58a73ec67a320a9d9ee9a29b8e0a4708aa40a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565897"
---
# <a name="modify-existing-registrar-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="860c2-103">Modificar as definições de configuração do registrador existentes no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="860c2-103">Modify existing Registrar configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="860c2-104">_**Última modificação do tópico:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="860c2-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="860c2-105">Você pode usar o Registrador para configurar protocolos de autenticação de servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="860c2-105">You can use the Registrar to configure proxy server authentication protocols.</span></span> <span data-ttu-id="860c2-106">Para obter informações sobre os protocolos disponíveis, consulte [Create registrar Configuration Settings in Lync Server 2013](lync-server-2013-create-registrar-configuration-settings.md).</span><span class="sxs-lookup"><span data-stu-id="860c2-106">For information about the available protocols, see [Create Registrar configuration settings in Lync Server 2013](lync-server-2013-create-registrar-configuration-settings.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="860c2-p102">É recomendável que você habilite Kerberos e NTLM quando um servidor oferecer suporte a autenticação a ambos, clientes remotos e corporativos. O Servidor de Borda e servidores internos se comunicam para garantir que somente a autenticação NTLM seja oferecida a clientes remotos. Se somente Kerberos estiver habilitada nesses servidores, eles não poderão autenticar usuários remotos. Se os usuários corporativos também se autenticarem no servidor, Kerberos será usada.</span><span class="sxs-lookup"><span data-stu-id="860c2-p102">We recommend that you enable both Kerberos and NTLM when a server supports authentication for both remote and enterprise clients. The Edge Server and internal servers communicate to ensure that only NTLM authentication is offered to remote clients. If only Kerberos is enabled on these servers, they cannot authenticate remote users. If enterprise users also authenticate against the server, Kerberos is used.</span></span>



</div>

<span data-ttu-id="860c2-111">Siga estas etapas para modificar um Registrador Avançado existente.</span><span class="sxs-lookup"><span data-stu-id="860c2-111">Follow these steps to modify an existing Registrar.</span></span>

<div>

## <a name="to-modify-existing-registrar-configuration-settings"></a><span data-ttu-id="860c2-112">Para modificar as definições de configuração do registrador existente</span><span class="sxs-lookup"><span data-stu-id="860c2-112">To modify existing registrar configuration settings</span></span>

1.  <span data-ttu-id="860c2-113">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que esteja na rede na qual você implantou o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="860c2-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="860c2-114">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="860c2-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="860c2-115">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="860c2-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="860c2-116">Na barra de navegação à esquerda, clique em **Segurança** e em **Registrador Avançado**.</span><span class="sxs-lookup"><span data-stu-id="860c2-116">In the left navigation bar, click **Security** and then click **Registrar**.</span></span>

4.  <span data-ttu-id="860c2-117">Na página **Registrador Avançado**, clique em um serviço, em **Editar** e em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="860c2-117">On the **Registrar** page, click a service, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="860c2-118">Em **Editar Configuração do Registrador Avançado**, selecione um ou mais dos itens a seguir, dependendo dos recursos dos clientes e do suporte em seu ambiente:</span><span class="sxs-lookup"><span data-stu-id="860c2-118">In **Edit Registrar Setting**, select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
      - <span data-ttu-id="860c2-119">**Habilitar autenticação Kerberos** para que os servidores no pool tratem desafios usando a autenticação Kerberos.</span><span class="sxs-lookup"><span data-stu-id="860c2-119">**Enable Kerberos authentication** to have the servers in the pool issue challenges using Kerberos authentication.</span></span>
    
      - <span data-ttu-id="860c2-120">**Habilitar autenticação NTLM** para que os servidores no pool emitam desafios usando NTLM.</span><span class="sxs-lookup"><span data-stu-id="860c2-120">**Enable NTLM authentication** to have the servers in the pool issue challenges using NTLM.</span></span>
    
      - <span data-ttu-id="860c2-121">**Habilitar autenticação de certificado** para que os servidores no pool emitam certificados aos clientes.</span><span class="sxs-lookup"><span data-stu-id="860c2-121">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>

6.  <span data-ttu-id="860c2-122">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="860c2-122">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

