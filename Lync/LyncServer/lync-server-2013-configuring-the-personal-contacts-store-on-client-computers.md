---
title: 'Lync Server 2013: Configurando o repositório de contatos pessoais em computadores cliente'
description: 'Lync Server 2013: Configurando o repositório de contatos pessoais em computadores cliente.'
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
ms.openlocfilehash: c1040b3eb9aa38e3e0c537d690b9292ab8f1ead2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544187"
---
# <a name="configuring-the-personal-contacts-store-on-client-computers-for-lync-server-2013"></a><span data-ttu-id="dc49c-103">Configurando o repositório de contatos pessoais em computadores clientes para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dc49c-103">Configuring the personal contacts store on client computers for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dc49c-104">_**Última modificação do tópico:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="dc49c-104">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="dc49c-105">Se você estiver integrando o Microsoft Lync Server 2013 e o Microsoft Exchange Server 2013, recomendamos que você configure o repositório de contatos pessoais em qualquer computador cliente executando o Microsoft Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="dc49c-105">If you are integrating Microsoft Lync Server 2013 and Microsoft Exchange Server 2013 then it is recommended that you configure the personal contact store on any client computers running Microsoft Lync 2010.</span></span> <span data-ttu-id="dc49c-106">Em particular, você deve configurar o Lync para usar o Exchange como o repositório de contatos pessoais e, ao mesmo tempo, garantir que os usuários não possam substituir essa decisão.</span><span class="sxs-lookup"><span data-stu-id="dc49c-106">In particular, you should configure Lync to use Exchange as the personal contact store, and, at the same time, ensure that users are not able to override that decision.</span></span> <span data-ttu-id="dc49c-107">Isso pode ser feito criando e configurando um valor de registro em cada computador cliente.</span><span class="sxs-lookup"><span data-stu-id="dc49c-107">This can be done by creating and configuring a Registry value on each client computer.</span></span>

<span data-ttu-id="dc49c-108">Observe que isso não é necessário em computadores que executam o Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="dc49c-108">Note that this is not required on computers running Lync 2013.</span></span>

<span data-ttu-id="dc49c-109">Para configurar esse valor em um único computador, execute os seguinte procedimento:</span><span class="sxs-lookup"><span data-stu-id="dc49c-109">To configure this value on a single computer, complete the following procedure:</span></span>

1.  <span data-ttu-id="dc49c-110">No computador cliente, clique em **Iniciar** e em **executar**.</span><span class="sxs-lookup"><span data-stu-id="dc49c-110">On the client computer, click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="dc49c-111">Na caixa de diálogo **executar** , digite regedit e pressione Enter.</span><span class="sxs-lookup"><span data-stu-id="dc49c-111">In the **Run** dialog box, type regedit and then press ENTER.</span></span>

3.  <span data-ttu-id="dc49c-112">No editor do registro, expanda **HKEY \_ local \_ Machine**, expanda **software**, expanda **Policies**, expanda **Microsoft**e, em seguida, expanda **Communicator**.</span><span class="sxs-lookup"><span data-stu-id="dc49c-112">In Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **Software**, expand **Policies**, expand **Microsoft**, and then expand **Communicator**.</span></span>

4.  <span data-ttu-id="dc49c-113">Clique com o botão direito do mouse em **Communicator**, aponte para **novo**e clique em **valor DWORD (32 bits)**.</span><span class="sxs-lookup"><span data-stu-id="dc49c-113">Right-click **Communicator**, point to **New**, and then click **DWORD (32-bit) Value**.</span></span>

5.  <span data-ttu-id="dc49c-114">Depois que o novo valor for criado, digite **PersonalContactStoreOverride** e pressione ENTER para renomear o valor.</span><span class="sxs-lookup"><span data-stu-id="dc49c-114">After the new value is created, type **PersonalContactStoreOverride** and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="dc49c-115">Verifique se o valor de PersonalContactStoreOverride está definido para 0 e feche o Editor do Registro.</span><span class="sxs-lookup"><span data-stu-id="dc49c-115">Verify that the value of PersonalContactStoreOverride is set to 0 and then close Registry Editor.</span></span>

<span data-ttu-id="dc49c-116">Se precisar fazer esta mesma alteração em vários computadores, você pode criar um objeto personalizado de Política de Grupo.</span><span class="sxs-lookup"><span data-stu-id="dc49c-116">If you need to make this same change on multiple computers you can do so by creating a custom Group Policy object.</span></span> <span data-ttu-id="dc49c-117">Para obter detalhes, consulte a documentação da política de grupo em [https://go.microsoft.com/fwlink/p/?LinkId=268543](https://go.microsoft.com/fwlink/p/?linkid=268543) .</span><span class="sxs-lookup"><span data-stu-id="dc49c-117">For details, see the Group Policy documentation at [https://go.microsoft.com/fwlink/p/?LinkId=268543](https://go.microsoft.com/fwlink/p/?linkid=268543).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

