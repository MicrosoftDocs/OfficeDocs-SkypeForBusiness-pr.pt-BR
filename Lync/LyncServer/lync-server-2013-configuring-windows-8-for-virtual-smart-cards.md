---
title: 'Lync Server 2013: Configurando o Windows 8 para cartões inteligentes virtuais'
description: 'Lync Server 2013: Configurando o Windows 8 para cartões inteligentes virtuais.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Windows 8 for Virtual Smart Cards
ms:assetid: 4916c167-4ee3-4f3e-b65c-33e588595112
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308564(v=OCS.15)
ms:contentKeyID: 54973684
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 112047f91a20dd552c628fb33eba7bb9ad3d0f01
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542157"
---
# <a name="configuring-windows-8-for-using-virtual-smart-cards-with-lync-server-2013"></a><span data-ttu-id="68d76-103">Configurando o Windows 8 para o uso de cartões inteligentes virtuais com o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68d76-103">Configuring Windows 8 for using Virtual Smart Cards with Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="68d76-104">_**Última modificação do tópico:** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="68d76-104">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="68d76-105">Um fator a ser considerado ao implantar a autenticação de dois fatores e a tecnologia de cartão inteligente é o custo da implementação.</span><span class="sxs-lookup"><span data-stu-id="68d76-105">One factor to consider when deploying two-factor authentication and smart card technology is the cost of implementation.</span></span> <span data-ttu-id="68d76-106">O Windows 8 oferece vários recursos de segurança novos e um dos novos recursos mais interessantes é o suporte para cartões inteligentes virtuais.</span><span class="sxs-lookup"><span data-stu-id="68d76-106">Windows 8 provides a number of new security capabilities, and one of the most interesting new features is support for virtual smart cards.</span></span>

<span data-ttu-id="68d76-107">Para computadores equipados com um chip TPM (Trusted Platform Module) que atende à versão 1,2 da especificação, as organizações agora podem obter os benefícios do logon do cartão inteligente sem fazer investimentos adicionais em hardware.</span><span class="sxs-lookup"><span data-stu-id="68d76-107">For computers equipped with a Trusted Platform Module (TPM) chip that meets specification version 1.2, organizations can now get the benefits of smart card logon without making any additional investments in hardware.</span></span> <span data-ttu-id="68d76-108">Para obter mais informações, consulte usando cartões inteligentes virtuais com o Windows 8 em [https://go.microsoft.com/fwlink/p/?LinkId=313365](https://go.microsoft.com/fwlink/p/?linkid=313365) .</span><span class="sxs-lookup"><span data-stu-id="68d76-108">For more information, see Using Virtual Smart Cards with Windows 8 at [https://go.microsoft.com/fwlink/p/?LinkId=313365](https://go.microsoft.com/fwlink/p/?linkid=313365).</span></span>

<div>

## <a name="to-configure-windows-8-for-virtual-smart-cards"></a><span data-ttu-id="68d76-109">Para configurar o Windows 8 para cartões inteligentes virtuais</span><span class="sxs-lookup"><span data-stu-id="68d76-109">To Configure Windows 8 for Virtual Smart Cards</span></span>

1.  <span data-ttu-id="68d76-110">Faça logon no computador com o Windows 8 usando as credenciais de um usuário habilitado para Lync.</span><span class="sxs-lookup"><span data-stu-id="68d76-110">Log in to the Windows 8 computer using the credentials of a Lync-enabled user.</span></span>

2.  <span data-ttu-id="68d76-111">Na tela inicial do Windows 8, mova o cursor para o canto inferior direito da tela.</span><span class="sxs-lookup"><span data-stu-id="68d76-111">At the Windows 8 Start screen, move your cursor to the bottom right corner of the screen.</span></span>

3.  <span data-ttu-id="68d76-112">Selecione a opção de **pesquisa** e procure o **prompt de comando**.</span><span class="sxs-lookup"><span data-stu-id="68d76-112">Select the **Search** option, and then search for **Command Prompt**.</span></span>

4.  <span data-ttu-id="68d76-113">Clique com o botão direito do mouse em **prompt de comando**e selecione **Executar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="68d76-113">Right click on **Command Prompt**, and then select **Run as Administrator**.</span></span>

5.  <span data-ttu-id="68d76-114">Abra o console de gerenciamento do Trusted Platform Module (TPM) executando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="68d76-114">Open the Trusted Platform Module (TPM) Management console by running the following command:</span></span>
    
        Tpm.msc

6.  <span data-ttu-id="68d76-115">No console de gerenciamento do TPM, verifique se a versão de especificação do TPM é pelo menos 1,2</span><span class="sxs-lookup"><span data-stu-id="68d76-115">From the TPM management console, verify that your TPM specification version is at least 1.2</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="68d76-116">Se você receber uma caixa de diálogo informando que um módulo de plataforma de confiança (TPM) compatível não pode ser encontrado, verifique se o computador tem um módulo TPM compatível e se está habilitado no BIOS do sistema.</span><span class="sxs-lookup"><span data-stu-id="68d76-116">If you receive a dialog stating that a Compatible Trust Platform Module (TPM) cannot be found, verify that the computer has a compatible TPM module and that it is enabled in the system BIOS.</span></span>

    
    </div>

7.  <span data-ttu-id="68d76-117">Fechar o console de gerenciamento do TPM</span><span class="sxs-lookup"><span data-stu-id="68d76-117">Close the TPM management console</span></span>

8.  <span data-ttu-id="68d76-118">No prompt de comando, crie um novo cartão inteligente virtual usando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="68d76-118">From the command prompt, create a new virtual smart card using the following command:</span></span>
    
        TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="68d76-119">Para fornecer um valor de PIN personalizado ao criar o cartão inteligente virtual, use o prompt/PIN em vez disso.</span><span class="sxs-lookup"><span data-stu-id="68d76-119">To provide a custom PIN value when creating the virtual smart card, use /pin prompt instead.</span></span>

    
    </div>

9.  <span data-ttu-id="68d76-120">No prompt de comando, abra o console de gerenciamento do computador executando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="68d76-120">From the command prompt, open the Computer Management console by running the following command:</span></span>
    
        CompMgmt.msc

10. <span data-ttu-id="68d76-121">No console de gerenciamento do computador, selecione **Gerenciamento de dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="68d76-121">In the Computer Management console, select **Device Management**.</span></span>

11. <span data-ttu-id="68d76-122">Expanda **leitores de cartões inteligentes**.</span><span class="sxs-lookup"><span data-stu-id="68d76-122">Expand **Smart card readers**.</span></span>

12. <span data-ttu-id="68d76-123">Verifique se o novo leitor de cartão inteligente virtual foi criado com êxito.</span><span class="sxs-lookup"><span data-stu-id="68d76-123">Verify that the new virtual smart card reader has been created successfully.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

