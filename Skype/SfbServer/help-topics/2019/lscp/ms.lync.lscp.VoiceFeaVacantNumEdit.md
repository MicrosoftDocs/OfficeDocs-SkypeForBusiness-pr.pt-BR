---
title: Número de telefone não atribuído Criar Novo ou Editar Existente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.VoiceFeaVacantNumEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 58903e40-6b93-40d6-88f8-1201743cd9be
ROBOTS: NOINDEX, NOFOLLOW
description: Números não atribuídos são números de telefone válidos para sua organização, mas que não são atribuídos a um usuário ou telefone. A tabela de números não atribuídos identifica como você deseja lidar com chamadas para números não atribuídos.
ms.openlocfilehash: 9cef4ae8075bf4982ab9c3ddd857062d4fa1a824
ms.sourcegitcommit: c477aa1a7da0b6b9bea1f5d10f1395eef418bfdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/10/2021
ms.locfileid: "50711728"
---
# <a name="unassigned-phone-number-create-new-or-edit-existing"></a><span data-ttu-id="768bc-104">Número de Telefone Não Atribuído: Criar Novo ou Editar Existente</span><span class="sxs-lookup"><span data-stu-id="768bc-104">Unassigned Phone Number: Create New or Edit Existing</span></span>

> [!NOTE]
> <span data-ttu-id="768bc-105">A UM do Exchange permanece disponível no Skype for Business Server 2019 quando você integra o Skype for Business 2019 com o Exchange 2013 ou o Exchange 2016.</span><span class="sxs-lookup"><span data-stu-id="768bc-105">Exchange UM remains available in Skype for Business Server 2019 when you integrate Skype for Business 2019 with Exchange 2013 or Exchange 2016.</span></span> <span data-ttu-id="768bc-106">Devido às alterações no suporte no Exchange 2019, a integração da UM do Exchange está sendo desalmada em favor dos recursos de Cloud Voicemail e Cloud Atendedor Automático.</span><span class="sxs-lookup"><span data-stu-id="768bc-106">Due to changes in support in Exchange 2019, Exchange UM integration is being de-emphasized in favor of Cloud Voicemail and Cloud Auto Attendant features.</span></span>

<span data-ttu-id="768bc-p103">Números não atribuídos são números de telefone válidos para sua organização, mas que não são atribuídos a um usuário ou telefone. A tabela de números não atribuídos identifica como você deseja lidar com chamadas para números não atribuídos.</span><span class="sxs-lookup"><span data-stu-id="768bc-p103">Unassigned numbers are phone numbers that are valid for your organization but are not assigned to a user or a phone. The unassigned number table identifies how you want calls to unassigned numbers to be treated.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="768bc-p104">Depois de concluir a criação de um novo intervalo de números não atribuídos ou editar um intervalo existente, clique em **OK** para retornar à página **Número Não Atribuído** que lista todos os intervalos de número. As alterações feitas na página **Novo Intervalo de Números Não Atribuídos** ou na página **Editar Intervalo de Números Não Atribuídos** não são confirmadas no banco de dados até que você clique em **Confirmar tudo** na página **Número Não Atribuído**.</span><span class="sxs-lookup"><span data-stu-id="768bc-p104">When you are finished creating a new unassigned number range or editing an existing one, click **OK** to return to the **Unassigned Number** page that lists all the number ranges. The changes you made on the **New Unassigned Number Range** page or the **Edit Unassigned Number Rage** page are not committed to the database until you click **Commit all** on the **Unassigned Number** page.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="768bc-111">Referência de UI</span><span class="sxs-lookup"><span data-stu-id="768bc-111">UI Reference</span></span>

<span data-ttu-id="768bc-112">A lista a seguir descreve os campos na página.</span><span class="sxs-lookup"><span data-stu-id="768bc-112">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="768bc-113">**Nome** Digite um nome descritivo que identifica o intervalo de números não atribuídos.</span><span class="sxs-lookup"><span data-stu-id="768bc-113">**Name** Type a descriptive name that identifies the unassigned number range.</span></span> <span data-ttu-id="768bc-114">Depois de salvar o intervalo, esse nome não pode ser alterado.</span><span class="sxs-lookup"><span data-stu-id="768bc-114">After you save the range, this name cannot be changed.</span></span>

- <span data-ttu-id="768bc-115">**Intervalo de números** No primeiro campo, digite o número inicial do intervalo de números não atribuídos.</span><span class="sxs-lookup"><span data-stu-id="768bc-115">**Number range** In the first field, type the beginning number of the unassigned number range.</span></span> <span data-ttu-id="768bc-116">No segundo campo, digite o número final do intervalo.</span><span class="sxs-lookup"><span data-stu-id="768bc-116">In the second field, type the ending number of the range.</span></span>

  - <span data-ttu-id="768bc-117">O número inicial do intervalo precisa ser menor ou igual ao número final do intervalo.</span><span class="sxs-lookup"><span data-stu-id="768bc-117">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

  - <span data-ttu-id="768bc-118">Se o número inicial do intervalo ou o número final do intervalo incluir um número de extensão, os números inicial e final do intervalo precisarão incluir uma extensão e o número de extensão deverá ser o mesmo para os números inicial e final.</span><span class="sxs-lookup"><span data-stu-id="768bc-118">If the beginning number of the range or the ending number of the range includes an extension number, both the beginning number and the ending number of the range must include an extension, and the extension number must be the same for both the beginning number and the ending number.</span></span>

  - <span data-ttu-id="768bc-119">O número deve corresponder à expressão regular ( `tel:` )?( \+ )? [1-9]\d {0,17} (;ext=[1-9]\d {0,9} )?.</span><span class="sxs-lookup"><span data-stu-id="768bc-119">The number must match the regular expression (`tel:`)?(\+)?[1-9]\d{0,17}(;ext=[1-9]\d{0,9})?.</span></span> <span data-ttu-id="768bc-120">Isso significa que o número pode começar com a cadeia de caracteres 'tel:'.</span><span class="sxs-lookup"><span data-stu-id="768bc-120">This means the number may begin with the string 'tel:'.</span></span> <span data-ttu-id="768bc-121">Se você não especificar essa cadeia de caracteres, ela será adicionada automaticamente para você, como um sinal de a mais (+) e um dígito de 1 a 9.</span><span class="sxs-lookup"><span data-stu-id="768bc-121">If you don't specify that string, it will be automatically added for you, such as a plus sign (+), and a digit 1 through 9.</span></span> <span data-ttu-id="768bc-122">O número de telefone pode ter até 17 dígitos e pode ser seguido por uma extensão no formato ;ext= seguido pelo número de extensão.</span><span class="sxs-lookup"><span data-stu-id="768bc-122">The phone number can be up to 17 digits and may be followed by an extension in the format ;ext= followed by the extension number.</span></span>

- <span data-ttu-id="768bc-123">**Serviço de comunicado** Selecione **Comunicado** para que o aplicativo Comunicado manipular a chamada de entrada ou a UM do Exchange para que um **um UM** do Exchange Atendedor Automático lidar com a chamada de entrada.</span><span class="sxs-lookup"><span data-stu-id="768bc-123">**Announcement service** Select **Announcement** to have the Announcement application handle the incoming call or **Exchange UM** to have an Exchange UM Auto Attendant handle the incoming call.</span></span>

- <span data-ttu-id="768bc-124">Se você tiver selecionado **Anúncio** para **Serviço de anúncio**:</span><span class="sxs-lookup"><span data-stu-id="768bc-124">If you selected **Announcement** for **Announcement service**:</span></span>

  - <span data-ttu-id="768bc-125">**FQDN do servidor de destino** Selecione a ID de serviço do serviço application que executa o aplicativo Comunicado que tratará de chamadas de entrada para esse intervalo de números não atribuídos.</span><span class="sxs-lookup"><span data-stu-id="768bc-125">**FQDN of destination server** Select the service ID of the Application service that runs the Announcement application that will handle incoming calls to this range of unassigned numbers.</span></span>

  - <span data-ttu-id="768bc-126">**Comunicado** Selecione o comunicado a ser tocado para esse intervalo de números não atribuídos.</span><span class="sxs-lookup"><span data-stu-id="768bc-126">**Announcement** Select the announcement to be played for this range of unassigned numbers.</span></span>

- <span data-ttu-id="768bc-127">Se você tiver selecionado **U do Exchange** para **Serviço de anúncio**:</span><span class="sxs-lookup"><span data-stu-id="768bc-127">If you selected **Exchange UM** for **Announcement service**:</span></span>

  - <span data-ttu-id="768bc-128">**Atendedor Automático telefone** Selecione o número de telefone do exchange um Atendedor Automático.</span><span class="sxs-lookup"><span data-stu-id="768bc-128">**Auto Attendant phone number** Select the phone number for the Exchange UM Auto Attendant.</span></span>

<span data-ttu-id="768bc-129">Para obter detalhes sobre recursos e recursos do Comunicado, consulte [Plan for the Announcement application in Skype for Business](../../../plan-your-deployment/enterprise-voice-solution/announcement.md) na documentação planejamento.</span><span class="sxs-lookup"><span data-stu-id="768bc-129">For details about Announcement features and capabilities, see [Plan for the Announcement application in Skype for Business](../../../plan-your-deployment/enterprise-voice-solution/announcement.md) in the Planning documentation.</span></span> <span data-ttu-id="768bc-130">Para obter detalhes sobre como trabalhar com intervalos de números não atribuídos, consulte [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) na documentação Operações.</span><span class="sxs-lookup"><span data-stu-id="768bc-130">For details about working with unassigned number ranges, see [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) in the Operations documentation.</span></span>


