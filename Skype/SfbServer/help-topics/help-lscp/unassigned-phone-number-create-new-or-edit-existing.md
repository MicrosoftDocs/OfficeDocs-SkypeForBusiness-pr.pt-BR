---
title: Número de telefone não atribuído criar novo ou editar existente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceFeaVacantNumEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58903e40-6b93-40d6-88f8-1201743cd9be
description: Números não atribuídos são números de telefone válidos para sua organização, mas que não são atribuídos a um usuário ou telefone. A tabela de números não atribuídos identifica como você deseja lidar com chamadas para números não atribuídos.
ms.openlocfilehash: 9af8cb8405bfb80e3d09eceb6f2cffa28a37c300
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34293029"
---
# <a name="unassigned-phone-number-create-new-or-edit-existing"></a><span data-ttu-id="5634a-104">Número de Telefone Não Atribuído: Criar Novo ou Editar Existente</span><span class="sxs-lookup"><span data-stu-id="5634a-104">Unassigned Phone Number: Create New or Edit Existing</span></span>

<span data-ttu-id="5634a-p102">Números não atribuídos são números de telefone válidos para sua organização, mas que não são atribuídos a um usuário ou telefone. A tabela de números não atribuídos identifica como você deseja lidar com chamadas para números não atribuídos.</span><span class="sxs-lookup"><span data-stu-id="5634a-p102">Unassigned numbers are phone numbers that are valid for your organization but are not assigned to a user or a phone. The unassigned number table identifies how you want calls to unassigned numbers to be treated.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5634a-107">Quando terminar de criar um novo intervalo de números não atribuídos ou editar um existente, clique em **OK** para retornar à página de **número não atribuído** que lista todos os intervalos de números.</span><span class="sxs-lookup"><span data-stu-id="5634a-107">When you are finished creating a new unassigned number range or editing an existing one, click **OK** to return to the **Unassigned Number** page that lists all the number ranges.</span></span> <span data-ttu-id="5634a-108">As alterações feitas na página **nova faixa de número não atribuída** ou **Editar número não atribuído da Rage** não são confirmadas para o banco de dados até que você clique em **confirmar tudo** na página **número não atribuído** .</span><span class="sxs-lookup"><span data-stu-id="5634a-108">The changes you made on the **New Unassigned Number Range** page or the **Edit Unassigned Number Rage** page are not committed to the database until you click **Commit all** on the **Unassigned Number** page.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="5634a-109">Referência de UI</span><span class="sxs-lookup"><span data-stu-id="5634a-109">UI Reference</span></span>

<span data-ttu-id="5634a-110">A lista a seguir descreve os campos na página.</span><span class="sxs-lookup"><span data-stu-id="5634a-110">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="5634a-111">**Nome** Digite um nome descritivo que identifique o intervalo numérico não atribuído.</span><span class="sxs-lookup"><span data-stu-id="5634a-111">**Name** Type a descriptive name that identifies the unassigned number range.</span></span> <span data-ttu-id="5634a-112">Depois de salvar o intervalo, esse nome não poderá ser alterado.</span><span class="sxs-lookup"><span data-stu-id="5634a-112">After you save the range, this name cannot be changed.</span></span>

- <span data-ttu-id="5634a-113">**Intervalo de números** No primeiro campo, digite o número inicial do intervalo numérico não atribuído.</span><span class="sxs-lookup"><span data-stu-id="5634a-113">**Number range** In the first field, type the beginning number of the unassigned number range.</span></span> <span data-ttu-id="5634a-114">No segundo campo, digite o número final do intervalo.</span><span class="sxs-lookup"><span data-stu-id="5634a-114">In the second field, type the ending number of the range.</span></span>

  - <span data-ttu-id="5634a-115">O número inicial do intervalo deve ser menor ou igual ao número final.</span><span class="sxs-lookup"><span data-stu-id="5634a-115">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

  - <span data-ttu-id="5634a-116">Se o número inicial ou o número final do intervalo incluir um número de ramal, ambos os números devem incluir um ramal, que deve ser o mesmo para ambos.</span><span class="sxs-lookup"><span data-stu-id="5634a-116">If the beginning number of the range or the ending number of the range includes an extension number, both the beginning number and the ending number of the range must include an extension, and the extension number must be the same for both the beginning number and the ending number.</span></span>

  - <span data-ttu-id="5634a-117">O número deve corresponder à expressão regular (Tel:) ? (\+) ? [1-9] \d{0,17}(; Ext = [1-9] \d{0,9}) ?.</span><span class="sxs-lookup"><span data-stu-id="5634a-117">The number must match the regular expression (tel:)?(\+)?[1-9]\d{0,17}(;ext=[1-9]\d{0,9})?.</span></span> <span data-ttu-id="5634a-118">Isso significa que o número pode começar com a cadeia de caracteres Tel: (se você não especificar essa cadeia de caracteres, ela será adicionada automaticamente para você), um sinal de adição (+) e um dígito de 1 a 9.</span><span class="sxs-lookup"><span data-stu-id="5634a-118">This means the number may begin with the string tel: (if you don't specify that string it will be automatically added for you), a plus sign (+), and a digit 1 through 9.</span></span> <span data-ttu-id="5634a-119">O número de telefone pode ter até 17 dígitos e pode ser seguido de um ramal no formato ;ext= seguido do número do ramal.</span><span class="sxs-lookup"><span data-stu-id="5634a-119">The phone number can be up to 17 digits and may be followed by an extension in the format ;ext= followed by the extension number.</span></span>

- <span data-ttu-id="5634a-120">**Serviço de anúncio** Selecione **anúncio** para que o aplicativo de anúncio manipule a chamada de entrada ou o **Exchange um** para que um atendedor automático de um Exchange trate a chamada de entrada.</span><span class="sxs-lookup"><span data-stu-id="5634a-120">**Announcement service** Select **Announcement** to have the Announcement application handle the incoming call or **Exchange UM** to have an Exchange UM Auto Attendant handle the incoming call.</span></span>

- <span data-ttu-id="5634a-121">Se você selecionou **anúncio** para **serviço de anúncio**:</span><span class="sxs-lookup"><span data-stu-id="5634a-121">If you selected **Announcement** for **Announcement service**:</span></span>

  - <span data-ttu-id="5634a-122">**FQDN do servidor de destino** Selecione a ID de serviço do serviço de aplicativo que executa o aplicativo de anúncio que manipulará as chamadas de entrada para essa faixa de números não atribuídos.</span><span class="sxs-lookup"><span data-stu-id="5634a-122">**FQDN of destination server** Select the service ID of the Application service that runs the Announcement application that will handle incoming calls to this range of unassigned numbers.</span></span>

  - <span data-ttu-id="5634a-123">**Aviso** Selecione o aviso a ser reproduzido para esse intervalo de números não atribuídos.</span><span class="sxs-lookup"><span data-stu-id="5634a-123">**Announcement** Select the announcement to be played for this range of unassigned numbers.</span></span>

- <span data-ttu-id="5634a-124">Se você selecionou o **Exchange um** para o **serviço de anúncio**:</span><span class="sxs-lookup"><span data-stu-id="5634a-124">If you selected **Exchange UM** for **Announcement service**:</span></span>

  - <span data-ttu-id="5634a-125">**Número de telefone do atendedor automático** Selecione o número de telefone para o atendedor automático de UM do Exchange.</span><span class="sxs-lookup"><span data-stu-id="5634a-125">**Auto Attendant phone number** Select the phone number for the Exchange UM Auto Attendant.</span></span>

<span data-ttu-id="5634a-126">Para obter detalhes sobre recursos e recursos do lançamento, consulte [planejar o aplicativo de anúncio no Skype for Business 2015](../../plan-your-deployment/enterprise-voice-solution/announcement.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="5634a-126">For details about Announcement features and capabilities, see [Plan for the Announcement application in Skype for Business 2015](../../plan-your-deployment/enterprise-voice-solution/announcement.md) in the Planning documentation.</span></span> <span data-ttu-id="5634a-127">Para obter detalhes sobre como trabalhar com intervalos de números não atribuídos, consulte  [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) na documentação Operações.</span><span class="sxs-lookup"><span data-stu-id="5634a-127">For details about working with unassigned number ranges, see [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) in the Operations documentation.</span></span>


