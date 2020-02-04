---
title: 'Lync Server 2013: atribuir uma política de correio de voz hospedada por usuário'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user hosted voice mail policy
ms:assetid: d44c71a0-4407-4ab4-b7e0-d671dde3425f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398919(v=OCS.15)
ms:contentKeyID: 48185456
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 95413733a9b23ce1f749ebb16521a3349b00165d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722951"
---
# <a name="assign-a-per-user-hosted-voice-mail-policy-in-lync-server-2013"></a><span data-ttu-id="2d1b3-102">Atribuir uma política de correio de voz hospedada por usuário no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2d1b3-102">Assign a per-user hosted voice mail policy in Lync Server 2013</span></span>

 


<span data-ttu-id="2d1b3-103">A implantação de uma ou mais políticas de correio de voz hospedadas por usuário é opcional.</span><span class="sxs-lookup"><span data-stu-id="2d1b3-103">Deploying one or more per-user hosted voice mail policies is optional.</span></span> <span data-ttu-id="2d1b3-104">Se você implantar políticas por usuário, deverá atribuí-las explicitamente a usuários, grupos ou objetos de contato.</span><span class="sxs-lookup"><span data-stu-id="2d1b3-104">If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact objects.</span></span>

<span data-ttu-id="2d1b3-105">Para obter detalhes sobre como atribuir ou remover a atribuição de políticas de correio de voz hospedadas por usuário, consulte a documentação do Shell de gerenciamento do Lync Server para os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="2d1b3-105">For details about assigning or removing the assignment of per-user hosted voice mail policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="2d1b3-106">Grant CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="2d1b3-106">Grant-CsHostedVoicemailPolicy</span></span>

  - <span data-ttu-id="2d1b3-107">Remove-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="2d1b3-107">Remove-CsHostedVoicemailPolicy</span></span>

## <a name="to-assign-a-per-user-hosted-voice-mail-policy"></a><span data-ttu-id="2d1b3-108">Para atribuir uma política de correio de voz hospedada por usuário</span><span class="sxs-lookup"><span data-stu-id="2d1b3-108">To assign a per-user hosted voice mail policy</span></span>

1.  <span data-ttu-id="2d1b3-109">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="2d1b3-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="2d1b3-110">Execute o cmdlet Grant-CsHostedVoicemailPolicy para atribuir a política de caixa postal hospedada por usuário a usuários individuais, grupos e objetos de contato.</span><span class="sxs-lookup"><span data-stu-id="2d1b3-110">Run the Grant-CsHostedVoicemailPolicy cmdlet to assign the per-user hosted voice mail policy to individual users, groups, and contact objects.</span></span> <span data-ttu-id="2d1b3-111">Por exemplo, execute:</span><span class="sxs-lookup"><span data-stu-id="2d1b3-111">For example, run:</span></span>
    
        Grant-CsHostedVoicemailPolicy -Identity "Ken Myer" -PolicyName ExRedmond
    
    <span data-ttu-id="2d1b3-112">Este exemplo atribuiu a política de caixa postal hospedada pela webmail ao usuário Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="2d1b3-112">This example assigned the ExRedmond hosted voice mail policy to user Ken Myer.</span></span>
    
    <span data-ttu-id="2d1b3-113">**Identidade** especifica a conta de usuário a ser modificada.</span><span class="sxs-lookup"><span data-stu-id="2d1b3-113">**Identity** specifies the user account to be modified.</span></span> <span data-ttu-id="2d1b3-114">O valor IDENTITY pode ser especificado usando qualquer um dos seguintes formatos:</span><span class="sxs-lookup"><span data-stu-id="2d1b3-114">The Identity value can be specified using any of the following formats:</span></span>
    
      - <span data-ttu-id="2d1b3-115">O endereço SIP do usuário</span><span class="sxs-lookup"><span data-stu-id="2d1b3-115">The user's SIP address</span></span>
    
      - <span data-ttu-id="2d1b3-116">O nome de usuário do Active Directory do usuário do Active Directory</span><span class="sxs-lookup"><span data-stu-id="2d1b3-116">The user's Active Directory User-Principal-Name</span></span>
    
      - <span data-ttu-id="2d1b3-117">O nome de logon\\do domínio do usuário (por exemplo\\, contoso kenmyer)</span><span class="sxs-lookup"><span data-stu-id="2d1b3-117">The user's domain\\logon name (for example, contoso\\kenmyer)</span></span>
    
      - <span data-ttu-id="2d1b3-118">O nome de exibição dos serviços de domínio Active Directory do usuário (por exemplo, Ken Myer).</span><span class="sxs-lookup"><span data-stu-id="2d1b3-118">The user's Active Directory Domain Services Display-Name (for example, Ken Myer).</span></span> <span data-ttu-id="2d1b3-119">Se estiver usando o nome de exibição como o valor de identidade, você poderá usar o\*caractere curinga asterisco ().</span><span class="sxs-lookup"><span data-stu-id="2d1b3-119">If using the Display-Name as the Identity value, you can use the asterisk (\*) wildcard character.</span></span> <span data-ttu-id="2d1b3-120">Por exemplo, a identidade "\* Smith" retorna todos os usuários que têm um nome de exibição que termina com o valor de cadeia de caracteres "Smith".</span><span class="sxs-lookup"><span data-stu-id="2d1b3-120">For example, the Identity "\* Smith" returns all the users who have a Display-Name that ends with the string value "Smith".</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="2d1b3-121">O nome de conta SAM do Active Directory do usuário não pode ser usado como o valor de identidade porque o SAM-Account-Name não é necessariamente exclusivo na floresta.</span><span class="sxs-lookup"><span data-stu-id="2d1b3-121">The user’s Active Directory SAM-Account-Name cannot be used as the Identity value because the SAM-Account-Name is not necessarily unique in the forest.</span></span>


