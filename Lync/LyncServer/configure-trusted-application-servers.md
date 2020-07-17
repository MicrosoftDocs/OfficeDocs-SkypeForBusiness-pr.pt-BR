---
title: Configurar os servidores de aplicativos confiáveis
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure trusted application servers
ms:assetid: 20c3815f-3048-4940-8c0f-cdfcd0801d5d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204735(v=OCS.15)
ms:contentKeyID: 48183592
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eb71833e782378f0d959fcbfcf5647235252e594
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754489"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-trusted-application-servers"></a><span data-ttu-id="bdc31-102">Configurar os servidores de aplicativos confiáveis</span><span class="sxs-lookup"><span data-stu-id="bdc31-102">Configure trusted application servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bdc31-103">_**Última modificação do tópico:** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="bdc31-103">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="bdc31-104">Em um ambiente misto, se você criar um novo servidor de aplicativos confiável, deverá definir o pool de próximo salto como um pool do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bdc31-104">In a mixed environment, if you create a new trusted application server, you must set the next hop pool to be a Lync Server 2013 pool.</span></span> <span data-ttu-id="bdc31-105">Em um ambiente misto, o pool herdado do Lync Server 2010 e o pool 2013 do Lync Server aparecem na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="bdc31-105">In a mixed environment, both the legacy Lync Server 2010 pool and the Lync Server 2013 pool appear in the drop down list.</span></span> <span data-ttu-id="bdc31-106">Selecionar o pool herdado não é suportado.</span><span class="sxs-lookup"><span data-stu-id="bdc31-106">Selecting the legacy pool is not supported.</span></span>

<span data-ttu-id="bdc31-107">**Selecionar Lync Server 2013 como próximo salto ao criar um servidor de aplicativos confiáveis**</span><span class="sxs-lookup"><span data-stu-id="bdc31-107">**Select Lync Server 2013 as next hop when creating a Trusted application server**</span></span>

1.  <span data-ttu-id="bdc31-108">Abra o Construtor de Topologia.</span><span class="sxs-lookup"><span data-stu-id="bdc31-108">Open Topology Builder.</span></span>

2.  <span data-ttu-id="bdc31-109">No painel esquerdo, clique com o botão direito em **Servidores de aplicativos confiáveis** e clique em **Novo pool de aplicativo confiável**.</span><span class="sxs-lookup"><span data-stu-id="bdc31-109">In the left pane, right click **Trusted application servers** and click **New Trusted Application Pool**.</span></span>

3.  <span data-ttu-id="bdc31-110">Insira o **FQDN do Pool** do pool de aplicativos confiáveis e selecione se será um servidor múltiplo ou único.</span><span class="sxs-lookup"><span data-stu-id="bdc31-110">Enter the **Pool FQDN** of the trusted application pool and select whether it will be a single-server or multiple-server.</span></span>

4.  <span data-ttu-id="bdc31-111">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="bdc31-111">Click **Next**.</span></span>

5.  <span data-ttu-id="bdc31-112">Na página **selecionar o próximo salto** , na lista, selecione o pool de front-ends do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bdc31-112">On the **Select the next hop** page, from the list, select the Lync Server 2013 Front End pool.</span></span>

6.  <span data-ttu-id="bdc31-113">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="bdc31-113">Click **Finish**.</span></span>

7.  <span data-ttu-id="bdc31-114">Selecione o nó superior **Lync Server** e no menu **Ações**, selecione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="bdc31-114">Select the top node **Lync Server** and from the **Action** menu, select **Publish**.</span></span>
    
    <span data-ttu-id="bdc31-115">Verifique se o \*\*Pool de Aplicativos Confiáveis \*\* foi criado com êxito e estará associado ao pool de Front-End correto.</span><span class="sxs-lookup"><span data-stu-id="bdc31-115">Verify the **Trusted Application Pool** has been created successfully and is associated with the correct Front End pool.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

