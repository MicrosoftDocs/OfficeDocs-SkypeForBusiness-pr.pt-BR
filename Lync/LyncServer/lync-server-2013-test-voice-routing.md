---
title: 'Lync Server 2013: Testar roteamento de voz'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test voice routing
ms:assetid: d3aae909-fef6-440f-b144-0b62dc82bf5d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398915(v=OCS.15)
ms:contentKeyID: 48185444
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0ac9fdac24178bfec7ebce97cbdfdd15707913d1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844665"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-voice-routing-in-lync-server-2013"></a><span data-ttu-id="0edd1-102">Testar roteamento de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0edd1-102">Test voice routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0edd1-103">_**Tópico da última modificação:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="0edd1-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="0edd1-104">Você pode usar a guia de roteamento de **voz** do painel de controle do Lync Server para configurar cenários de casos de teste.</span><span class="sxs-lookup"><span data-stu-id="0edd1-104">You can use the Lync Server Control Panel **Test Voice Routing** tab to configure test case scenarios.</span></span> <span data-ttu-id="0edd1-105">Para definir um caso de teste, especifique o plano de discagem, a política de voz, o uso da PSTN e a rota de voz em que deseja testar um número de telefone especificado.</span><span class="sxs-lookup"><span data-stu-id="0edd1-105">To define a test case, you specify the dial plan, voice policy, PSTN usage, and voice route against which to test a specified phone number.</span></span>

<span data-ttu-id="0edd1-106">Antes de realmente implantar sua configuração de roteamento de voz, recomendamos testá-la em vários números de telefone para ter certeza de que os resultados são o que você está esperando.</span><span class="sxs-lookup"><span data-stu-id="0edd1-106">Before you actually deploy your voice routing configuration, we recommend that you test it on various phone numbers to make sure that the results are what you're expecting.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="0edd1-107">Você pode usar os comandos <STRONG>Exportar casos de teste</STRONG> e <STRONG>importar casos de teste</STRONG> para salvar os casos de teste de roteamento de voz e importá-los para uso em outro computador.</span><span class="sxs-lookup"><span data-stu-id="0edd1-107">You can use the <STRONG>Export test cases</STRONG> and <STRONG>Import test cases</STRONG> commands to save voice routing test cases and import them for use on another computer.</span></span>



</div>

<div>


> [!WARNING]  
> <span data-ttu-id="0edd1-108">Se você excluir qualquer parte de sua configuração de roteamento de voz, como um plano de discagem, política de voz, rota de voz ou uso do telefone, você deve revisar e atualizar seus casos de teste de roteamento de voz.</span><span class="sxs-lookup"><span data-stu-id="0edd1-108">If you delete any part of your voice routing configuration, such as a dial plan, voice policy, voice route, or phone usage, you should review and update your voice routing test cases.</span></span> <span data-ttu-id="0edd1-109">O painel de controle do Lync Server não irá alertá-lo para testar casos que não sejam mais válidos devido às configurações alteradas.</span><span class="sxs-lookup"><span data-stu-id="0edd1-109">The Lync Server Control Panel will not alert you to test cases that are no longer valid due to changed configurations.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="0edd1-110">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="0edd1-110">In This Section</span></span>

  - [<span data-ttu-id="0edd1-111">Criar um caso de teste de roteamento de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0edd1-111">Create a voice routing test case in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-routing-test-case.md)

  - [<span data-ttu-id="0edd1-112">Exportar casos de teste de roteamento de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0edd1-112">Export voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-export-voice-routing-test-cases.md)

  - [<span data-ttu-id="0edd1-113">Importar casos de teste de roteamento de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0edd1-113">Import voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-import-voice-routing-test-cases.md)

  - [<span data-ttu-id="0edd1-114">Executando testes de roteamento de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0edd1-114">Running voice routing tests in Lync Server 2013</span></span>](lync-server-2013-running-voice-routing-tests.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

