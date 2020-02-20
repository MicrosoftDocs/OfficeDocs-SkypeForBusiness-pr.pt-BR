---
title: 'Lync Server 2013: entrar e usar o Lync 2013 na máquina virtual'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Signing in and using Lync 2013 on the virtual machine
ms:assetid: 6140fc19-5bef-4b58-9b0f-19112b5ecd00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204948(v=OCS.15)
ms:contentKeyID: 48184318
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e638fd734f00633b22664b4d4862733eb6d078da
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142747"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="signing-in-and-using-lync-2013-on-the-virtual-machine"></a><span data-ttu-id="a12c4-102">Entrar e usar o Lync 2013 na máquina virtual</span><span class="sxs-lookup"><span data-stu-id="a12c4-102">Signing in and using Lync 2013 on the virtual machine</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a12c4-103">_**Última modificação do tópico:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="a12c4-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="a12c4-104">Depois que o plug-in VDI estiver habilitado, as seguintes etapas ocorrerão quando o usuário entrar no Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="a12c4-104">After the VDI plug-in is enabled, the following steps occur when the user signs in to Lync 2013.</span></span>

1.  <span data-ttu-id="a12c4-105">O usuário digita suas credenciais no cliente do Lync 2013 em execução na máquina virtual.</span><span class="sxs-lookup"><span data-stu-id="a12c4-105">The user types his or her credentials in to the Lync 2013 client running on the virtual machine.</span></span>

2.  <span data-ttu-id="a12c4-106">Depois que o Lync detectar a disponibilidade do plug-in VDI, o Lync solicitará que o usuário insira novamente suas credenciais.</span><span class="sxs-lookup"><span data-stu-id="a12c4-106">After Lync detects the availability of the VDI plug-in, Lync prompts the user to re-enter his or her credentials.</span></span> <span data-ttu-id="a12c4-107">Nessa caixa de diálogo, é recomendável que o usuário marque a caixa de seleção **Salvar minha senha** para que não precise inserir as credenciais na próxima entrada.</span><span class="sxs-lookup"><span data-stu-id="a12c4-107">In this dialog box, we recommend that the user select the **Save my password** check box so that he or she will not be required to enter credentials during subsequent sign in.</span></span>

3.  <span data-ttu-id="a12c4-108">O Lync começa a emparelhar com o plug-in VDI.</span><span class="sxs-lookup"><span data-stu-id="a12c4-108">Lync begins pairing with the VDI plug-in.</span></span> <span data-ttu-id="a12c4-109">Antes que o emparelhamento seja concluído, o cliente exibe dois ícones na barra de status do Lync.</span><span class="sxs-lookup"><span data-stu-id="a12c4-109">Before pairing is complete, the client displays two icons in the Lync status bar.</span></span> <span data-ttu-id="a12c4-110">O ícone no canto inferior esquerdo indica que nenhum dispositivo de áudio está disponível, e o ícone piscante no canto inferior direito indica que o emparelhamento de VDI está em andamento:</span><span class="sxs-lookup"><span data-stu-id="a12c4-110">The icon in the lower left indicates that no audio devices are available, and the blinking icon in the lower right indicates that the VDI pairing is in progress, as shown:</span></span>
    
    <span data-ttu-id="a12c4-111">![Ícone do Lync VDI mostrando emparelhamento bem-sucedido](images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "Ícone do Lync VDI mostrando emparelhamento bem-sucedido")</span><span class="sxs-lookup"><span data-stu-id="a12c4-111">![Lync VDI icon showing successful pairing](images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "Lync VDI icon showing successful pairing")</span></span>  

4.  <span data-ttu-id="a12c4-112">Após o emparelhamento bem-sucedido de VDI, os ícones mudarão para indicar o dispositivo de áudio que será usado para chamadas e o êxito do emparelhamento de VDI:</span><span class="sxs-lookup"><span data-stu-id="a12c4-112">After VDI pairing is successful, the icons change to indicate the audio device that will be used for calls and the VDI pairing success:</span></span>
    
    <span data-ttu-id="a12c4-113">![Ícone de emparelhamento de VDI do Lync mostrando êxito](images/JJ204948.57be3387-a3e5-4949-831e-f5ff9fcc5598(OCS.15).png "Ícone de emparelhamento de VDI do Lync mostrando êxito")</span><span class="sxs-lookup"><span data-stu-id="a12c4-113">![Lync VDI pairing icon showing success](images/JJ204948.57be3387-a3e5-4949-831e-f5ff9fcc5598(OCS.15).png "Lync VDI pairing icon showing success")</span></span>  

5.  <span data-ttu-id="a12c4-114">Após os pares do Lync com o plug-in VDI, o usuário pode ver sua presença em dispositivos compatíveis com Lync conectados ao computador local.</span><span class="sxs-lookup"><span data-stu-id="a12c4-114">After Lync pairs with the VDI plug-in, the user can see his or her presence on Lync compatible devices that are connected to the local computer.</span></span> <span data-ttu-id="a12c4-115">Agora, o usuário poderá realizar e atender chamadas como de costume.</span><span class="sxs-lookup"><span data-stu-id="a12c4-115">The user can now place and answer calls as usual.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

