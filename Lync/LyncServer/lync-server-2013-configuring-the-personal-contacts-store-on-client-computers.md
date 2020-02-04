---
title: 'Lync Server 2013: Configurando o repositório de contatos pessoais em computadores cliente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the personal contacts store on client computers
ms:assetid: ec69a6cb-07f2-4057-9544-55035f83eeae
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721922(v=OCS.15)
ms:contentKeyID: 49733857
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77e6e48593bb3dc7a11375b13346ad59b2f40c0e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734621"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-personal-contacts-store-on-client-computers-for-lync-server-2013"></a><span data-ttu-id="d6c74-102">Configurando o repositório de contatos pessoais em computadores cliente para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d6c74-102">Configuring the personal contacts store on client computers for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d6c74-103">_**Tópico da última modificação:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="d6c74-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="d6c74-104">Se você estiver integrando o Microsoft Lync Server 2013 e o Microsoft Exchange Server 2013, recomendamos que você configure o repositório de contatos pessoais em qualquer computador cliente que esteja executando o Microsoft Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="d6c74-104">If you are integrating Microsoft Lync Server 2013 and Microsoft Exchange Server 2013 then it is recommended that you configure the personal contact store on any client computers running Microsoft Lync 2010.</span></span> <span data-ttu-id="d6c74-105">Em particular, você deve configurar o Lync para usar o Exchange como o repositório de contatos pessoais e, ao mesmo tempo, certificar-se de que os usuários não podem substituir essa decisão.</span><span class="sxs-lookup"><span data-stu-id="d6c74-105">In particular, you should configure Lync to use Exchange as the personal contact store, and, at the same time, ensure that users are not able to override that decision.</span></span> <span data-ttu-id="d6c74-106">Isso pode ser feito com a criação e configuração de um valor de Registro em cada computador cliente.</span><span class="sxs-lookup"><span data-stu-id="d6c74-106">This can be done by creating and configuring a Registry value on each client computer.</span></span>

<span data-ttu-id="d6c74-107">Observe que isso não é necessário em computadores que executam o Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="d6c74-107">Note that this is not required on computers running Lync 2013.</span></span>

<span data-ttu-id="d6c74-108">Para configurar esse valor em um único computador, execute os seguinte procedimento:</span><span class="sxs-lookup"><span data-stu-id="d6c74-108">To configure this value on a single computer, complete the following procedure:</span></span>

1.  <span data-ttu-id="d6c74-109">No computador do cliente, clique em **Iniciar**, e então clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="d6c74-109">On the client computer, click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="d6c74-110">Na caixa de diálogo **Executar**, digite regedit e depois pressione ENTER.</span><span class="sxs-lookup"><span data-stu-id="d6c74-110">In the **Run** dialog box, type regedit and then press ENTER.</span></span>

3.  <span data-ttu-id="d6c74-111">No editor do registro, expanda **HKEY\_local\_Machine**, expanda **software**, expanda **políticas**, expanda Microsoft e, em seguida, expanda **o** **Communicator**.</span><span class="sxs-lookup"><span data-stu-id="d6c74-111">In Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **Software**, expand **Policies**, expand **Microsoft**, and then expand **Communicator**.</span></span>

4.  <span data-ttu-id="d6c74-112">Clique com o botão direito do mouse em **Communicator**, aponte para **Novo** e clique no **Valor DWORD (32 bits)**.</span><span class="sxs-lookup"><span data-stu-id="d6c74-112">Right-click **Communicator**, point to **New**, and then click **DWORD (32-bit) Value**.</span></span>

5.  <span data-ttu-id="d6c74-113">Depois do novo valor ser criado, digite **PersonalContactStoreOverride** e pressione ENTER para renomear o valor.</span><span class="sxs-lookup"><span data-stu-id="d6c74-113">After the new value is created, type **PersonalContactStoreOverride** and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="d6c74-114">Verifique se o valor de PersonalContactStoreOverride está definido para 0 e feche o Editor do Registro.</span><span class="sxs-lookup"><span data-stu-id="d6c74-114">Verify that the value of PersonalContactStoreOverride is set to 0 and then close Registry Editor.</span></span>

<span data-ttu-id="d6c74-115">Se precisar fazer esta mesma alteração em vários computadores, você pode criar um objeto personalizado de Política de Grupo.</span><span class="sxs-lookup"><span data-stu-id="d6c74-115">If you need to make this same change on multiple computers you can do so by creating a custom Group Policy object.</span></span> <span data-ttu-id="d6c74-116">Para obter detalhes, consulte a documentação da política [http://go.microsoft.com/fwlink/p/?LinkId=268543](http://go.microsoft.com/fwlink/p/?linkid=268543)de grupo em.</span><span class="sxs-lookup"><span data-stu-id="d6c74-116">For details, see the Group Policy documentation at [http://go.microsoft.com/fwlink/p/?LinkId=268543](http://go.microsoft.com/fwlink/p/?linkid=268543).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

