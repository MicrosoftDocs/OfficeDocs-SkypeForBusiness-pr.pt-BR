---
title: 'Lync Server 2013: importar casos de teste de roteamento de voz'
description: 'Lync Server 2013: importar casos de teste de roteamento de voz.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Import voice routing test cases
ms:assetid: 6546e24c-9ad2-428b-92b2-63948ed0f884
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398460(v=OCS.15)
ms:contentKeyID: 48184325
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06ce1b144de03406b7b78d6957371ed2bc303e95
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547827"
---
# <a name="import-voice-routing-test-cases-in-lync-server-2013"></a><span data-ttu-id="0dec9-103">Importar casos de teste de roteamento de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0dec9-103">Import voice routing test cases in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0dec9-104">_**Última modificação do tópico:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="0dec9-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="0dec9-105">Os casos de teste fornecem uma maneira de testar as rotas de voz em sua organização: você define coisas como o número a ser discado e o plano de discagem e a política de voz a serem empregados, e o Lync Server 2013 pode então verificar se, dadas essas condições, o número fornecido pode ser roteado com êxito para a rede PSTN.</span><span class="sxs-lookup"><span data-stu-id="0dec9-105">Test cases provide a way for you to test voice routes in your organization: you define such things as the number to be dialed and the dial plan and voice policy to be employed, and Lync Server 2013 can then verify that, given those conditions, the supplied number can successfully be routed to the PSTN network.</span></span>

<span data-ttu-id="0dec9-106">Os casos de teste, que podem ser criados usando o painel de controle do Lync Server, são normalmente salvos somente no servidor onde o caso foi originalmente criado e executado.</span><span class="sxs-lookup"><span data-stu-id="0dec9-106">Test cases, which can be created by using Lync Server Control Panel, are typically saved only on the server where the case was originally created and run.</span></span> <span data-ttu-id="0dec9-107">No entanto, esses casos de teste podem ser exportados como arquivos XML (com a extensão. vtest) e importados em outros servidores.</span><span class="sxs-lookup"><span data-stu-id="0dec9-107">However, these test cases can be exported as XML files (with the .vtest extension) and then imported on other servers.</span></span> <span data-ttu-id="0dec9-108">Isso permite que você execute os mesmos testes em computadores diferentes localizados em diferentes pontos da sua topologia.</span><span class="sxs-lookup"><span data-stu-id="0dec9-108">This enables you to run the same tests on different computers located at different points in your topology.</span></span>

<div>

## <a name="to-import-a-voice-routing-test-case"></a><span data-ttu-id="0dec9-109">Para importar um caso de teste de roteamento de voz</span><span class="sxs-lookup"><span data-stu-id="0dec9-109">To import a voice routing test case</span></span>

1.  <span data-ttu-id="0dec9-110">Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="0dec9-110">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="0dec9-111">Para obter detalhes, consulte [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="0dec9-111">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="0dec9-112">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0dec9-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="0dec9-113">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="0dec9-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="0dec9-114">Na barra de navegação esquerda, clique em **Roteamento de Voz**.</span><span class="sxs-lookup"><span data-stu-id="0dec9-114">In the left navigation bar, click **Voice Routing**.</span></span>

4.  <span data-ttu-id="0dec9-115">No menu **ações** , clique em **importar casos de teste**.</span><span class="sxs-lookup"><span data-stu-id="0dec9-115">On the **Actions** menu, click **Import test cases**.</span></span>

5.  <span data-ttu-id="0dec9-116">Localize o arquivo de caso de teste (. vtest) que você deseja importar e clique em **abrir**.</span><span class="sxs-lookup"><span data-stu-id="0dec9-116">Find the test case file (.vtest) that you want to import, and then click **Open**.</span></span>

6.  <span data-ttu-id="0dec9-117">Clique em **Confirmar** e clique em **Confirmar tudo**.</span><span class="sxs-lookup"><span data-stu-id="0dec9-117">Click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0dec9-118">Sempre que você importa um arquivo. vtest, deve executar o comando <STRONG>confirmar tudo</STRONG> para publicar o caso de teste.</span><span class="sxs-lookup"><span data-stu-id="0dec9-118">Whenever you import a .vtest file, you must run the <STRONG>Commit all</STRONG> command to publish the test case.</span></span> <span data-ttu-id="0dec9-119">Para obter detalhes, consulte <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish Pending Changes to The Voice Routing Configuration in Lync Server 2013</A> na documentação operações.</span><span class="sxs-lookup"><span data-stu-id="0dec9-119">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0dec9-120">Confira também</span><span class="sxs-lookup"><span data-stu-id="0dec9-120">See Also</span></span>


[<span data-ttu-id="0dec9-121">Exportar casos de teste de roteamento de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0dec9-121">Export voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-export-voice-routing-test-cases.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

