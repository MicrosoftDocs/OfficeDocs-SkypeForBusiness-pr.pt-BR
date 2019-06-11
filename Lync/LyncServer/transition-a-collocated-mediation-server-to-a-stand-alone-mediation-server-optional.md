---
title: Fazer a transição de um servidor de mediação posicionado para um servidor autônomo de mediação (opcional)
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Transition a collocated Mediation Server to a stand-alone Mediation Server (optional)
ms:assetid: 7c3c2fb4-4ff2-47b1-aab3-0aa91472eadb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205026(v=OCS.15)
ms:contentKeyID: 48184602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c49b75845bb9a673872c5f08225dd6e1c96b69a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844134"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server-optional"></a><span data-ttu-id="b4684-102">Fazer a transição de um servidor de mediação posicionado para um servidor autônomo de mediação (opcional)</span><span class="sxs-lookup"><span data-stu-id="b4684-102">Transition a collocated Mediation Server to a stand-alone Mediation Server (optional)</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b4684-103">_**Tópico da última modificação:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="b4684-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="b4684-104">Use o procedimento a seguir para fazer a transição do servidor de mediação, posicionado no seu servidor Standard Edition ou no pool Front-end, em um servidor autônomo de mediação para uma implantação de um único site.</span><span class="sxs-lookup"><span data-stu-id="b4684-104">Use the procedure that follows to transition your Mediation Server, collocated on your Standard Edition server or Front End pool, to a stand-alone Mediation Server for a single-site deployment.</span></span>

<div>

## <a name="to-transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server"></a><span data-ttu-id="b4684-105">Para fazer a transição de um servidor de mediação posicionado para um servidor de mediação autônomo</span><span class="sxs-lookup"><span data-stu-id="b4684-105">To transition a collocated Mediation Server to a stand-alone Mediation Server</span></span>

1.  <span data-ttu-id="b4684-106">Abra uma topologia existente do construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="b4684-106">Open an existing topology from Topology Builder.</span></span>

2.  <span data-ttu-id="b4684-107">No painel esquerdo, navegue até pools de **mediação**.</span><span class="sxs-lookup"><span data-stu-id="b4684-107">In the left pane, navigate to **Mediation pools**.</span></span>

3.  <span data-ttu-id="b4684-108">Clique com o \*\*\*\* botão direito em pools de mediação e selecione **novo servidor**de mediação.</span><span class="sxs-lookup"><span data-stu-id="b4684-108">Right-click **Mediation pools** and select **New Mediation Server**.</span></span>

4.  <span data-ttu-id="b4684-109">Na página **definir novo pool** de mediação, forneça o FQDN do novo pool do servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="b4684-109">On the **Define New Mediation Pool** page, provide the FQDN of the new Mediation Server pool.</span></span> <span data-ttu-id="b4684-110">Além disso, selecione se este pool será um pool de servidor único ou de vários servidores e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b4684-110">Also, select whether this pool will be a single-server or multiple-server pool, and then click **Next**.</span></span>

5.  <span data-ttu-id="b4684-111">Selecione o pool do servidor front-end de salto seguinte para o qual o novo servidor de mediação roteará chamadas de entrada e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b4684-111">Select the next hop Front End server pool to which the new Mediation Server will route inbound calls, and then click **Next**.</span></span>

6.  <span data-ttu-id="b4684-112">Selecione o pool de bordas a ser usado pelo servidor de mediação e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b4684-112">Select the Edge pool to be used by the Mediation Server and then click **Next**.</span></span>

7.  <span data-ttu-id="b4684-113">Na página **especificar gateways PSTN** , associe o gateway PSTN anterior ao servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="b4684-113">On the **Specify PSTN gateways** page, associate the previous PSTN gateway with the Mediation Server.</span></span> <span data-ttu-id="b4684-114">Selecione o gateway e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="b4684-114">Select the gateway and then click **Add**.</span></span>

8.  <span data-ttu-id="b4684-115">Clique em **concluir** para fechar o assistente para **definir novo pool** de mediação.</span><span class="sxs-lookup"><span data-stu-id="b4684-115">Click **Finish** to close the **Define New Mediation Pool** wizard.</span></span>

9.  <span data-ttu-id="b4684-116">No **Construtor**de topologias, selecione o nó superior do **Lync Server 2013**.</span><span class="sxs-lookup"><span data-stu-id="b4684-116">From **Topology Builder**, select the top node **Lync Server 2013**.</span></span>

10. <span data-ttu-id="b4684-117">No painel **ações** , selecione **publicar topologia** e conclua o assistente.</span><span class="sxs-lookup"><span data-stu-id="b4684-117">From the **Actions** pane, select **Publish Topology** and complete the wizard.</span></span>

11. <span data-ttu-id="b4684-118">Siga as etapas em [instalar os arquivos para o servidor de mediação no Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md) na documentação de implantação para instalar os arquivos no novo servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="b4684-118">Follow the steps in [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md) in the Deployment documentation to install the files on the new Mediation Server.</span></span>

12. <span data-ttu-id="b4684-119">Após a instalação dos arquivos no servidor de mediação, retorne ao construtor de topologias e, no painel esquerdo, navegue até o pool.</span><span class="sxs-lookup"><span data-stu-id="b4684-119">After the files are installed on the Mediation Server, return to Topology Builder, and in the left pane navigate to the pool.</span></span>

13. <span data-ttu-id="b4684-120">Clique com o botão direito do mouse no pool e selecione **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="b4684-120">Right-click the pool and select **Edit Properties**.</span></span>

14. <span data-ttu-id="b4684-121">Em **servidor**de mediação, desmarque a caixa de seleção posicionada no **servidor** de mediação posicionado e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="b4684-121">Under **Mediation Server**, clear the check box **Collocated Mediation Server enabled** and then click **OK**.</span></span>

15. <span data-ttu-id="b4684-122">No **Construtor**de topologias, selecione o nó superior do **Lync Server 2013**.</span><span class="sxs-lookup"><span data-stu-id="b4684-122">From **Topology Builder**, select the top node **Lync Server 2013**.</span></span>

16. <span data-ttu-id="b4684-123">No menu **ação** , selecione **publicar topologia** e conclua o assistente.</span><span class="sxs-lookup"><span data-stu-id="b4684-123">From the **Action** menu, select **Publish Topology** and complete the wizard.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

