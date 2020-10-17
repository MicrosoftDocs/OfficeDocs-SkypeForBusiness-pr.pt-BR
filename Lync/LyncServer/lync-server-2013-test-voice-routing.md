---
title: 'Lync Server 2013: testar roteamento de voz'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test voice routing
ms:assetid: d3aae909-fef6-440f-b144-0b62dc82bf5d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398915(v=OCS.15)
ms:contentKeyID: 48185444
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0643c0d7da4dbed734bfd098cc2a585e018bf0cd
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532938"
---
# <a name="test-voice-routing-in-lync-server-2013"></a><span data-ttu-id="522ca-102">Testar roteamento de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="522ca-102">Test voice routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="522ca-103">_**Última modificação do tópico:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="522ca-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="522ca-104">Você pode usar a guia de roteamento de **voz de teste** do painel de controle do Lync Server para configurar cenários de caso de teste.</span><span class="sxs-lookup"><span data-stu-id="522ca-104">You can use the Lync Server Control Panel **Test Voice Routing** tab to configure test case scenarios.</span></span> <span data-ttu-id="522ca-105">Para definir um caso de teste, especifique o plano de discagem, a política de voz, o uso de PSTN e a rota de voz na qual testar um número de telefone especificado.</span><span class="sxs-lookup"><span data-stu-id="522ca-105">To define a test case, you specify the dial plan, voice policy, PSTN usage, and voice route against which to test a specified phone number.</span></span>

<span data-ttu-id="522ca-106">Antes de realmente implantar sua configuração de roteamento de voz, recomendamos testá-lo em vários números de telefone para garantir que os resultados sejam o que você espera.</span><span class="sxs-lookup"><span data-stu-id="522ca-106">Before you actually deploy your voice routing configuration, we recommend that you test it on various phone numbers to make sure that the results are what you're expecting.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="522ca-107">Também é possível usar os comandos <STRONG>Exportar casos de teste</STRONG> e <STRONG>Importar casos de teste</STRONG> para salvar os casos de teste de roteamento de voz e importá-los para uso em outro computador.</span><span class="sxs-lookup"><span data-stu-id="522ca-107">You can use the <STRONG>Export test cases</STRONG> and <STRONG>Import test cases</STRONG> commands to save voice routing test cases and import them for use on another computer.</span></span>



</div>

<div>


> [!WARNING]  
> <span data-ttu-id="522ca-108">Se você excluir qualquer parte de sua configuração de roteamento de voz, como um plano de discagem, política de voz, rota de voz ou uso de telefone, revise e atualize seus casos de teste de roteamento de voz.</span><span class="sxs-lookup"><span data-stu-id="522ca-108">If you delete any part of your voice routing configuration, such as a dial plan, voice policy, voice route, or phone usage, you should review and update your voice routing test cases.</span></span> <span data-ttu-id="522ca-109">O painel de controle do Lync Server não alertará você para testar casos que não são mais válidos devido às configurações alteradas.</span><span class="sxs-lookup"><span data-stu-id="522ca-109">The Lync Server Control Panel will not alert you to test cases that are no longer valid due to changed configurations.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="522ca-110">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="522ca-110">In This Section</span></span>

  - [<span data-ttu-id="522ca-111">Criar um caso de teste de roteamento de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="522ca-111">Create a voice routing test case in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-routing-test-case.md)

  - [<span data-ttu-id="522ca-112">Exportar casos de teste de roteamento de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="522ca-112">Export voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-export-voice-routing-test-cases.md)

  - [<span data-ttu-id="522ca-113">Importar casos de teste de roteamento de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="522ca-113">Import voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-import-voice-routing-test-cases.md)

  - [<span data-ttu-id="522ca-114">Executando testes de roteamento de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="522ca-114">Running voice routing tests in Lync Server 2013</span></span>](lync-server-2013-running-voice-routing-tests.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

