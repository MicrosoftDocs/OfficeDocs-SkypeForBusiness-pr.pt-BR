---
title: Configurar os servidores de aplicativos confiáveis
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure trusted application servers
ms:assetid: 47a9e72e-566c-4c23-bec2-760a3098a974
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204865(v=OCS.15)
ms:contentKeyID: 48184056
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7e74cba866a7353890bb47de745e5e525d43963
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006587"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-trusted-application-servers"></a><span data-ttu-id="2b632-102">Configurar os servidores de aplicativos confiáveis</span><span class="sxs-lookup"><span data-stu-id="2b632-102">Configure trusted application servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2b632-103">_**Última modificação do tópico:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="2b632-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="2b632-104">Em um ambiente misto, se você criar um novo servidor de aplicativos confiável após mesclar a topologia herdada do Office Communications Server com o Lync Server 2013 e definir um novo servidor de aplicativos confiável usando o construtor de topologias, você deve definir o próximo pool de salto como um Pool do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2b632-104">In a mixed environment, if you create a new trusted application server after merging the legacy Office Communications Server topology with Lync Server 2013, and you define a new trusted application server using Topology Builder, you must set the next hop pool to be a Lync Server 2013 pool.</span></span> <span data-ttu-id="2b632-105">Em um ambiente mesclado, o pool herdado do Office Communications Server e o pool do Lync Server 2013 aparecem na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="2b632-105">In a merged environment, both the legacy Office Communications Server pool and the Lync Server 2013 pool appear in the drop down list.</span></span> <span data-ttu-id="2b632-106">*Não* é permitido selecionar o pool herdado.</span><span class="sxs-lookup"><span data-stu-id="2b632-106">Selecting the legacy pool is *not* supported.</span></span>

<div>

## <a name="to-select-lync-server-2013-as-next-hop-when-creating-a-trusted-application-server"></a><span data-ttu-id="2b632-107">Para selecionar o Lync Server 2013 como próximo salto ao criar um servidor de aplicativos confiáveis</span><span class="sxs-lookup"><span data-stu-id="2b632-107">To select Lync Server 2013 as next hop when creating a Trusted application server</span></span>

1.  <span data-ttu-id="2b632-108">Abra uma topologia existente no Construtor de Topologia.</span><span class="sxs-lookup"><span data-stu-id="2b632-108">Open an existing topology in Topology Builder.</span></span>

2.  <span data-ttu-id="2b632-109">No painel à esquerda, clique com o botão direito do mouse em **Servidores de aplicativos confiáveis** e clique em **Novo pool de aplicativo confiável**.</span><span class="sxs-lookup"><span data-stu-id="2b632-109">In the left pane, right click **Trusted application servers** and click **New Trusted Application Pool**.</span></span>

3.  <span data-ttu-id="2b632-110">Insira o **Pool FQDN** para o pool de aplicativo confiável e selecione se será uma implantação de servidor único ou de vários servidores.</span><span class="sxs-lookup"><span data-stu-id="2b632-110">Enter the **Pool FQDN** of the trusted application pool and select whether it will be a single-server or multiple-server deployment.</span></span>

4.  <span data-ttu-id="2b632-111">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="2b632-111">Click **Next**.</span></span>

5.  <span data-ttu-id="2b632-112">Na página **selecionar o próximo salto** , na lista, selecione o pool de front-ends do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2b632-112">On the **Select the next hop** page, from the list, select the Lync Server 2013 Front End pool.</span></span>
    
    <span data-ttu-id="2b632-113">![Caixa de diálogo Definir novo pool de aplicativos confiáveis](images/JJ204865.ecfe2bb8-758b-4b36-8146-573005c4ab09(OCS.15).jpg "Caixa de diálogo Definir novo pool de aplicativos confiáveis")</span><span class="sxs-lookup"><span data-stu-id="2b632-113">![Define New Trusted Application Pool dialog](images/JJ204865.ecfe2bb8-758b-4b36-8146-573005c4ab09(OCS.15).jpg "Define New Trusted Application Pool dialog")</span></span>  

6.  <span data-ttu-id="2b632-114">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="2b632-114">Click **Finish**.</span></span>

7.  <span data-ttu-id="2b632-115">Selecione o nó superior **Servidor Lync** e, do painel **Ações**, selecione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="2b632-115">Select the top node **Lync Server** and from the **Actions** pane, select **Publish**.</span></span>

8.  <span data-ttu-id="2b632-116">Verifique se o **Pool de aplicativo confiável** foi criado com êxito e associado ao pool de Front End correto.</span><span class="sxs-lookup"><span data-stu-id="2b632-116">Verify the **Trusted Application Pool** was created successfully and is associated with the correct Front End pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

