---
title: Número de telefone não atribuídos criar novo ou editar existente
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceFeaVacantNumEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58903e40-6b93-40d6-88f8-1201743cd9be
ROBOTS: NOINDEX, NOFOLLOW
description: Números não atribuídos são números de telefone válidos para sua organização, mas que não são atribuídos a um usuário ou telefone. A tabela de números não atribuídos identifica como você deseja lidar com chamadas para números não atribuídos.
ms.openlocfilehash: 6df9574bb6d999e4800c727f6cbabe0aa68818e9
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/28/2018
ms.locfileid: "23244192"
---
# <a name="unassigned-phone-number-create-new-or-edit-existing"></a><span data-ttu-id="62cc1-104">Número de telefone não atribuído: Criar nova ou editar existente</span><span class="sxs-lookup"><span data-stu-id="62cc1-104">Unassigned Phone Number: Create New or Edit Existing</span></span>

> [!NOTE]
> <span data-ttu-id="62cc1-105">UM do Exchange permanece disponível na Skype para Business Server 2019 ao integrar Skype para negócios 2019 com Exchange 2013 ou 2016 do Exchange.</span><span class="sxs-lookup"><span data-stu-id="62cc1-105">Exchange UM remains available in Skype for Business Server 2019 when you integrate Skype for Business 2019 with Exchange 2013 or Exchange 2016.</span></span> <span data-ttu-id="62cc1-106">Devido às alterações no suporte no Exchange 2019, a integração de UM do Exchange está sendo desprovisionamento emphasised em favor de recursos de caixa postal de nuvem e atendedor automático de nuvem.</span><span class="sxs-lookup"><span data-stu-id="62cc1-106">Due to changes in support in Exchange 2019, Exchange UM integration is being de-emphasised in favor of Cloud Voicemail and Cloud Auto Attendant features.</span></span>

<span data-ttu-id="62cc1-p103">Números não atribuídos são números de telefone válidos para sua organização, mas que não são atribuídos a um usuário ou telefone. A tabela de números não atribuídos identifica como você deseja lidar com chamadas para números não atribuídos.</span><span class="sxs-lookup"><span data-stu-id="62cc1-p103">Unassigned numbers are phone numbers that are valid for your organization but are not assigned to a user or a phone. The unassigned number table identifies how you want calls to unassigned numbers to be treated.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="62cc1-109">Quando terminar de criar um novo intervalo de números não atribuído ou editando uma existente, clique em **Okey** para retornar à página de **Número não atribuído** que lista todos os intervalos de números.</span><span class="sxs-lookup"><span data-stu-id="62cc1-109">When you are finished creating a new unassigned number range or editing an existing one, click **OK** to return to the **Unassigned Number** page that lists all the number ranges.</span></span> <span data-ttu-id="62cc1-110">As alterações feitas na página **Novo Unassigned Number Range** ou a página **Editar moda de número não atribuídos** não são confirmadas no banco de dados até que você clique **em Confirmar tudo** na página **Número não atribuído** .</span><span class="sxs-lookup"><span data-stu-id="62cc1-110">The changes you made on the **New Unassigned Number Range** page or the **Edit Unassigned Number Rage** page are not committed to the database until you click **Commit all** on the **Unassigned Number** page.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="62cc1-111">Referência de UI</span><span class="sxs-lookup"><span data-stu-id="62cc1-111">UI Reference</span></span>

<span data-ttu-id="62cc1-112">A lista a seguir descreve os campos na página.</span><span class="sxs-lookup"><span data-stu-id="62cc1-112">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="62cc1-113">**Nome** Digite um nome descritivo que identifica o intervalo de números não atribuído.</span><span class="sxs-lookup"><span data-stu-id="62cc1-113">**Name** Type a descriptive name that identifies the unassigned number range.</span></span> <span data-ttu-id="62cc1-114">Depois de salvar o intervalo, esse nome não pode ser alterado.</span><span class="sxs-lookup"><span data-stu-id="62cc1-114">After you save the range, this name cannot be changed.</span></span>

- <span data-ttu-id="62cc1-115">**Intervalo de número** No primeiro campo, digite o número inicial do intervalo de números não atribuído.</span><span class="sxs-lookup"><span data-stu-id="62cc1-115">**Number range** In the first field, type the beginning number of the unassigned number range.</span></span> <span data-ttu-id="62cc1-116">No segundo campo, digite o número final do intervalo.</span><span class="sxs-lookup"><span data-stu-id="62cc1-116">In the second field, type the ending number of the range.</span></span>

  - <span data-ttu-id="62cc1-117">O número inicial do intervalo deve ser menor ou igual ao número final.</span><span class="sxs-lookup"><span data-stu-id="62cc1-117">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

  - <span data-ttu-id="62cc1-118">Se o número inicial ou o número final do intervalo incluir um número de ramal, ambos os números devem incluir um ramal, que deve ser o mesmo para ambos.</span><span class="sxs-lookup"><span data-stu-id="62cc1-118">If the beginning number of the range or the ending number of the range includes an extension number, both the beginning number and the ending number of the range must include an extension, and the extension number must be the same for both the beginning number and the ending number.</span></span>

  - <span data-ttu-id="62cc1-119">Os números devem corresponder à expressão regular (tel:) ? (\+) ? [1-9] \d{0,17}(; ext = [1-9] \d{0,9}) ?.</span><span class="sxs-lookup"><span data-stu-id="62cc1-119">The number must match the regular expression (tel:)?(\+)?[1-9]\d{0,17}(;ext=[1-9]\d{0,9})?.</span></span> <span data-ttu-id="62cc1-120">Isso significa que o número pode começar com o cadeia de caracteres tel: (se você não especificar uma cadeia de caracteres ele será automaticamente adicionado para você), um sinal de adição (+) e um dígito entre 1 e 9.</span><span class="sxs-lookup"><span data-stu-id="62cc1-120">This means the number may begin with the string tel: (if you don't specify that string it will be automatically added for you), a plus sign (+), and a digit 1 through 9.</span></span> <span data-ttu-id="62cc1-121">O número de telefone pode ter até 17 dígitos e pode ser seguido de um ramal no formato ;ext=, seguido do número do ramal.</span><span class="sxs-lookup"><span data-stu-id="62cc1-121">The phone number can be up to 17 digits and may be followed by an extension in the format ;ext= followed by the extension number.</span></span>

- <span data-ttu-id="62cc1-122">**Serviço de comunicado** Selecione **comunicado** ter o aplicativo de anúncio de lidar com a chamada de entrada ou **UM do Exchange** para ter uma Exchange atendedor automático de UM lidar com a chamada de entrada.</span><span class="sxs-lookup"><span data-stu-id="62cc1-122">**Announcement service** Select **Announcement** to have the Announcement application handle the incoming call or **Exchange UM** to have an Exchange UM Auto Attendant handle the incoming call.</span></span>

- <span data-ttu-id="62cc1-123">Se você tiver selecionado **anúncio** para **serviço de anúncio**:</span><span class="sxs-lookup"><span data-stu-id="62cc1-123">If you selected **Announcement** for **Announcement service**:</span></span>

  - <span data-ttu-id="62cc1-124">**FQDN do servidor de destino** Selecione o ID de serviço do serviço aplicativo que executa o aplicativo de anúncio que lidará com as chamadas de entrada para esse intervalo de números não atribuídos.</span><span class="sxs-lookup"><span data-stu-id="62cc1-124">**FQDN of destination server** Select the service ID of the Application service that runs the Announcement application that will handle incoming calls to this range of unassigned numbers.</span></span>

  - <span data-ttu-id="62cc1-125">**Comunicado** Selecione o anúncio a ser reproduzido para esse intervalo de números não atribuídos.</span><span class="sxs-lookup"><span data-stu-id="62cc1-125">**Announcement** Select the announcement to be played for this range of unassigned numbers.</span></span>

-  <span data-ttu-id="62cc1-126">Se você tiver selecionado **UM do Exchange** para **serviço de anúncio**:</span><span class="sxs-lookup"><span data-stu-id="62cc1-126">If you selected **Exchange UM** for **Announcement service**:</span></span>

  - <span data-ttu-id="62cc1-127">**Número de telefone do atendedor automático** Selecione o número de telefone para o Atendedor de automático UM do Exchange.</span><span class="sxs-lookup"><span data-stu-id="62cc1-127">**Auto Attendant phone number** Select the phone number for the Exchange UM Auto Attendant.</span></span>

<span data-ttu-id="62cc1-128">Para obter detalhes sobre o comunicado recursos e capacidades, consulte o [plano para o aplicativo de anúncio no Skype para negócios](../../../plan-your-deployment/enterprise-voice-solution/announcement.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="62cc1-128">For details about Announcement features and capabilities, see [Plan for the Announcement application in Skype for Business](../../../plan-your-deployment/enterprise-voice-solution/announcement.md) in the Planning documentation.</span></span> <span data-ttu-id="62cc1-129">Para obter detalhes sobre como trabalhar com intervalos de números não atribuídos, consulte [Configurar o roteamento de números não atribuídos telefone](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) na documentação operações.</span><span class="sxs-lookup"><span data-stu-id="62cc1-129">For details about working with unassigned number ranges, see [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) in the Operations documentation.</span></span>


