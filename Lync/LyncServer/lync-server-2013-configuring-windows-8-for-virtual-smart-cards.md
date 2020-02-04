---
title: 'Lync Server 2013: Configurando o Windows 8 para cartões inteligentes virtuais'
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
ms.openlocfilehash: b6298f7aa6a500a71c0b3732dd2f3d180e7192d3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733641"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-windows-8-for-using-virtual-smart-cards-with-lync-server-2013"></a><span data-ttu-id="751a4-102">Configurar o Windows 8 para usar cartões inteligentes virtuais com o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="751a4-102">Configuring Windows 8 for using Virtual Smart Cards with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="751a4-103">_**Tópico da última modificação:** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="751a4-103">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="751a4-104">Um fator que deve ser levado em consideração na implantação da autenticação de dois fatores e na tecnologia de cartão inteligente é o custo da implementação.</span><span class="sxs-lookup"><span data-stu-id="751a4-104">One factor to consider when deploying two-factor authentication and smart card technology is the cost of implementation.</span></span> <span data-ttu-id="751a4-105">O Windows 8 fornece vários recursos de segurança novos, e um dos novos recursos mais interessantes é o suporte para cartões inteligentes virtuais.</span><span class="sxs-lookup"><span data-stu-id="751a4-105">Windows 8 provides a number of new security capabilities, and one of the most interesting new features is support for virtual smart cards.</span></span>

<span data-ttu-id="751a4-106">Para computadores que contam com um chip Trusted Platform Module (TPM) compatível com a especificação da versão 1.2, as organizações podem agora se beneficiar do logon com cartões inteligentes sem fazer mais nenhum investimento em hardware.</span><span class="sxs-lookup"><span data-stu-id="751a4-106">For computers equipped with a Trusted Platform Module (TPM) chip that meets specification version 1.2, organizations can now get the benefits of smart card logon without making any additional investments in hardware.</span></span> <span data-ttu-id="751a4-107">Para obter mais informações, consulte usando cartões inteligentes virtuais com o Windows [http://go.microsoft.com/fwlink/p/?LinkId=313365](http://go.microsoft.com/fwlink/p/?linkid=313365)8 em.</span><span class="sxs-lookup"><span data-stu-id="751a4-107">For more information, see Using Virtual Smart Cards with Windows 8 at [http://go.microsoft.com/fwlink/p/?LinkId=313365](http://go.microsoft.com/fwlink/p/?linkid=313365).</span></span>

<div>

## <a name="to-configure-windows-8-for-virtual-smart-cards"></a><span data-ttu-id="751a4-108">Para configurar o Windows 8 para cartões inteligentes virtuais</span><span class="sxs-lookup"><span data-stu-id="751a4-108">To Configure Windows 8 for Virtual Smart Cards</span></span>

1.  <span data-ttu-id="751a4-109">Faça logon no computador com o Windows 8 usando as credenciais de um usuário compatível com o Lync.</span><span class="sxs-lookup"><span data-stu-id="751a4-109">Log in to the Windows 8 computer using the credentials of a Lync-enabled user.</span></span>

2.  <span data-ttu-id="751a4-110">Na tela Iniciar do Windows 8, mova seu cursor para o canto inferior direito da tela.</span><span class="sxs-lookup"><span data-stu-id="751a4-110">At the Windows 8 Start screen, move your cursor to the bottom right corner of the screen.</span></span>

3.  <span data-ttu-id="751a4-111">Selecione a opção **Pesquisar** e pesquise **Command Prompt**.</span><span class="sxs-lookup"><span data-stu-id="751a4-111">Select the **Search** option, and then search for **Command Prompt**.</span></span>

4.  <span data-ttu-id="751a4-112">Clique com o botão direito do mouse em **Prompt de comando** e selecione **Executar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="751a4-112">Right click on **Command Prompt**, and then select **Run as Administrator**.</span></span>

5.  <span data-ttu-id="751a4-113">Abra o Console de Gerenciamento do Trusted Platform Module (TPM) executando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="751a4-113">Open the Trusted Platform Module (TPM) Management console by running the following command:</span></span>
    
        Tpm.msc

6.  <span data-ttu-id="751a4-114">No Console de Gerenciamento do TPM, confira se a versão do seu TPM é 1.2 ou superior.</span><span class="sxs-lookup"><span data-stu-id="751a4-114">From the TPM management console, verify that your TPM specification version is at least 1.2</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="751a4-115">Caso surja uma caixa de diálogo com a mensagem de que não foi possível encontrar o Trust Platform Module (TPM) compatível, verifique se o computador tem um módulo TPM compatível e se ele está habilitado na BIOS do sistema.</span><span class="sxs-lookup"><span data-stu-id="751a4-115">If you receive a dialog stating that a Compatible Trust Platform Module (TPM) cannot be found, verify that the computer has a compatible TPM module and that it is enabled in the system BIOS.</span></span>

    
    </div>

7.  <span data-ttu-id="751a4-116">Feche o Console de Gerenciamento do TPM</span><span class="sxs-lookup"><span data-stu-id="751a4-116">Close the TPM management console</span></span>

8.  <span data-ttu-id="751a4-117">No prompt de comando, crie um novo cartão inteligente virtual usando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="751a4-117">From the command prompt, create a new virtual smart card using the following command:</span></span>
    
        TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="751a4-118">Para personalizar o valor do PIN ao criar o cartão inteligente virtual, use o prompt /pin.</span><span class="sxs-lookup"><span data-stu-id="751a4-118">To provide a custom PIN value when creating the virtual smart card, use /pin prompt instead.</span></span>

    
    </div>

9.  <span data-ttu-id="751a4-119">No prompt de comando, abre o Console de Gerenciamento do computador executando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="751a4-119">From the command prompt, open the Computer Management console by running the following command:</span></span>
    
        CompMgmt.msc

10. <span data-ttu-id="751a4-120">No Console de Gerenciamento do computador, selecione **Gerenciamento de Dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="751a4-120">In the Computer Management console, select **Device Management**.</span></span>

11. <span data-ttu-id="751a4-121">Expanda **Leitores de cartão inteligente**.</span><span class="sxs-lookup"><span data-stu-id="751a4-121">Expand **Smart card readers**.</span></span>

12. <span data-ttu-id="751a4-122">Verifique se o novo leitor de cartão inteligente virtual foi criado com êxito.</span><span class="sxs-lookup"><span data-stu-id="751a4-122">Verify that the new virtual smart card reader has been created successfully.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

