---
title: 'Lync Server 2013: Exportar casos de teste de roteamento de voz'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Export voice routing test cases
ms:assetid: 489ac472-1a35-4755-b390-48f7cdf31e94
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425957(v=OCS.15)
ms:contentKeyID: 48184050
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 781c9e312044193cb6195ee849a880bea6e08485
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756215"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="export-voice-routing-test-cases-in-lync-server-2013"></a><span data-ttu-id="e26f8-102">Exportar casos de teste de roteamento de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e26f8-102">Export voice routing test cases in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e26f8-103">_**Tópico da última modificação:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="e26f8-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="e26f8-104">Os casos de teste fornecem uma maneira de testar as rotas de voz em sua organização: você define itens como o número a ser discado e o plano de discagem e a política de voz a ser empregado, e o Lync Server pode, em seguida, verificar se, dadas essas condições, o número fornecido pode foi roteada com êxito para a rede PSTN.</span><span class="sxs-lookup"><span data-stu-id="e26f8-104">Test cases provide a way for you to test voice routes in your organization: you define such things as the number to be dialed and the dial plan and voice policy to be employed, and Lync Server can then verify that, given those conditions, the supplied number can successfully be routed to the PSTN network.</span></span>

<span data-ttu-id="e26f8-105">Os casos de teste, que podem ser criados usando o painel de controle do Lync Server, geralmente são salvos apenas no servidor em que o caso foi originalmente criado e executado.</span><span class="sxs-lookup"><span data-stu-id="e26f8-105">Test cases, which can be created by using Lync Server Control Panel, are typically saved only on the server where the case was originally created and run.</span></span> <span data-ttu-id="e26f8-106">No entanto, esses casos de teste podem ser exportados como arquivos XML (com a extensão. vtest) e depois importados em outros servidores.</span><span class="sxs-lookup"><span data-stu-id="e26f8-106">However, these test cases can be exported as XML files (with the .vtest extension) and then imported on other servers.</span></span> <span data-ttu-id="e26f8-107">Isso permite que você execute os mesmos testes em computadores diferentes localizados em diferentes pontos da topologia.</span><span class="sxs-lookup"><span data-stu-id="e26f8-107">This enables you to run the same tests on different computers located at different points in your topology.</span></span>

<div>

## <a name="to-export-a-voice-routing-test-case"></a><span data-ttu-id="e26f8-108">Para exportar um caso de teste de roteamento de voz</span><span class="sxs-lookup"><span data-stu-id="e26f8-108">To export a voice routing test case</span></span>

1.  <span data-ttu-id="e26f8-109">No painel de controle do Lync Server, clique em **Roteamento de voz** e, em seguida, clique em **testar roteamento de voz**.</span><span class="sxs-lookup"><span data-stu-id="e26f8-109">In Lync Server Control Panel, click **Voice Routing** and then click **Test Voice Routing**.</span></span>

2.  <span data-ttu-id="e26f8-110">Na guia **Roteamento de voz de teste** , selecione o caso de teste (ou casos de teste) a ser exportado.</span><span class="sxs-lookup"><span data-stu-id="e26f8-110">On the **Test Voice Routing** tab, select the test case (or test cases) to be exported.</span></span> <span data-ttu-id="e26f8-111">Para selecionar vários casos de teste, clique no primeiro caso para ser exportado, mantenha a tecla Ctrl pressionada e selecione os casos adicionais a serem exportados.</span><span class="sxs-lookup"><span data-stu-id="e26f8-111">To select multiple test cases, click the first case to be exported, then hold down the Ctrl key and select the additional cases to be exported.</span></span>

3.  <span data-ttu-id="e26f8-112">Clique em **ação**e, em seguida, clique em **Exportar casos de teste**.</span><span class="sxs-lookup"><span data-stu-id="e26f8-112">Click **Action**, then click **Export test cases**.</span></span>

4.  <span data-ttu-id="e26f8-113">Na caixa de diálogo **salvar como** , selecione uma pasta para armazenar os casos de teste exportados e digite um nome para o arquivo XML resultante na caixa **nome do arquivo** .</span><span class="sxs-lookup"><span data-stu-id="e26f8-113">In the **Save As** dialog box, select a folder to store the exported test cases and type a name for the resulting XML file in the **File name** box.</span></span> <span data-ttu-id="e26f8-114">Observe que, se você estiver exportando vários casos vários testes, todos esses casos de teste serão salvos em um único arquivo XML.</span><span class="sxs-lookup"><span data-stu-id="e26f8-114">Note that if you are exporting multiple tests cases all of these test cases will be saved to a single XML file.</span></span>

5.  <span data-ttu-id="e26f8-115">Para salvar os casos de teste, clique em **salvar**.</span><span class="sxs-lookup"><span data-stu-id="e26f8-115">To save the test cases, click **Save**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e26f8-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="e26f8-116">See Also</span></span>


[<span data-ttu-id="e26f8-117">Importar casos de teste de roteamento de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e26f8-117">Import voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-import-voice-routing-test-cases.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

