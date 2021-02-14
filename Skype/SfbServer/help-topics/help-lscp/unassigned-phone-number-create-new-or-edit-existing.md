---
title: Número de Telefone Não Atribuído Criar Novo ou Editar Existente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.VoiceFeaVacantNumEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58903e40-6b93-40d6-88f8-1201743cd9be
description: Números não atribuídos são números de telefone válidos para sua organização, mas que não são atribuídos a um usuário ou telefone. A tabela de números não atribuídos identifica como você deseja lidar com chamadas para números não atribuídos.
ms.openlocfilehash: 741068fc16c60e6cd253057a8b1487680dc32266
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818791"
---
# <a name="unassigned-phone-number-create-new-or-edit-existing"></a><span data-ttu-id="56e62-104">Número de Telefone Não Atribuído: Criar Novo ou Editar Existente</span><span class="sxs-lookup"><span data-stu-id="56e62-104">Unassigned Phone Number: Create New or Edit Existing</span></span>

<span data-ttu-id="56e62-p102">Números não atribuídos são números de telefone válidos para sua organização, mas que não são atribuídos a um usuário ou telefone. A tabela de números não atribuídos identifica como você deseja lidar com chamadas para números não atribuídos.</span><span class="sxs-lookup"><span data-stu-id="56e62-p102">Unassigned numbers are phone numbers that are valid for your organization but are not assigned to a user or a phone. The unassigned number table identifies how you want calls to unassigned numbers to be treated.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="56e62-p103">Depois de concluir a criação de um novo intervalo de números não atribuídos ou editar um intervalo existente, clique em **OK** para retornar à página **Número Não Atribuído** que lista todos os intervalos de número. As alterações feitas na página **Novo Intervalo de Números Não Atribuídos** ou na página **Editar Intervalo de Números Não Atribuídos** não são confirmadas no banco de dados até que você clique em **Confirmar tudo** na página **Número Não Atribuído**.</span><span class="sxs-lookup"><span data-stu-id="56e62-p103">When you are finished creating a new unassigned number range or editing an existing one, click **OK** to return to the **Unassigned Number** page that lists all the number ranges. The changes you made on the **New Unassigned Number Range** page or the **Edit Unassigned Number Rage** page are not committed to the database until you click **Commit all** on the **Unassigned Number** page.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="56e62-109">Referência de UI</span><span class="sxs-lookup"><span data-stu-id="56e62-109">UI Reference</span></span>

<span data-ttu-id="56e62-110">A lista a seguir descreve os campos na página.</span><span class="sxs-lookup"><span data-stu-id="56e62-110">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="56e62-111">**Nome** Digite um nome descritivo que identifique o intervalo de números não atribuídos.</span><span class="sxs-lookup"><span data-stu-id="56e62-111">**Name** Type a descriptive name that identifies the unassigned number range.</span></span> <span data-ttu-id="56e62-112">Depois de salvar o intervalo, esse nome não pode ser alterado.</span><span class="sxs-lookup"><span data-stu-id="56e62-112">After you save the range, this name cannot be changed.</span></span>

- <span data-ttu-id="56e62-113">**Intervalo de números** No primeiro campo, digite o número inicial do intervalo de números não atribuídos.</span><span class="sxs-lookup"><span data-stu-id="56e62-113">**Number range** In the first field, type the beginning number of the unassigned number range.</span></span> <span data-ttu-id="56e62-114">No segundo campo, digite o número final do intervalo.</span><span class="sxs-lookup"><span data-stu-id="56e62-114">In the second field, type the ending number of the range.</span></span>

  - <span data-ttu-id="56e62-115">O número inicial do intervalo precisa ser menor ou igual ao número final do intervalo.</span><span class="sxs-lookup"><span data-stu-id="56e62-115">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

  - <span data-ttu-id="56e62-116">Se o número inicial do intervalo ou o número final do intervalo incluir um número de extensão, os números inicial e final do intervalo precisarão incluir uma extensão e o número de extensão deverá ser o mesmo para os números inicial e final.</span><span class="sxs-lookup"><span data-stu-id="56e62-116">If the beginning number of the range or the ending number of the range includes an extension number, both the beginning number and the ending number of the range must include an extension, and the extension number must be the same for both the beginning number and the ending number.</span></span>

  - <span data-ttu-id="56e62-117">O número deve corresponder à expressão regular (tel:)?( \+ )? [1-9]\d {0,17} (;ext=[1-9]\d {0,9} )?.</span><span class="sxs-lookup"><span data-stu-id="56e62-117">The number must match the regular expression (tel:)?(\+)?[1-9]\d{0,17}(;ext=[1-9]\d{0,9})?.</span></span> <span data-ttu-id="56e62-118">Isso significa que o número pode começar com a cadeia de caracteres tel: (se você não especificar essa cadeia de caracteres, ele será adicionado automaticamente para você), um sinal de mais (+) e um dígito de 1 a 9.</span><span class="sxs-lookup"><span data-stu-id="56e62-118">This means the number may begin with the string tel: (if you don't specify that string it will be automatically added for you), a plus sign (+), and a digit 1 through 9.</span></span> <span data-ttu-id="56e62-119">O número de telefone pode ter até 17 dígitos e pode ser seguido por uma extensão no formato ;ext= seguido pelo número de extensão.</span><span class="sxs-lookup"><span data-stu-id="56e62-119">The phone number can be up to 17 digits and may be followed by an extension in the format ;ext= followed by the extension number.</span></span>

- <span data-ttu-id="56e62-120">**Serviço de comunicados** Selecione **Comunicado para** que o aplicativo Comunicado manipular a chamada de entrada ou a UM do **Exchange** para que um Atendente Automático do UM do Exchange manipular a chamada de entrada.</span><span class="sxs-lookup"><span data-stu-id="56e62-120">**Announcement service** Select **Announcement** to have the Announcement application handle the incoming call or **Exchange UM** to have an Exchange UM Auto Attendant handle the incoming call.</span></span>

- <span data-ttu-id="56e62-121">Se você tiver selecionado **Anúncio** para **Serviço de anúncio**:</span><span class="sxs-lookup"><span data-stu-id="56e62-121">If you selected **Announcement** for **Announcement service**:</span></span>

  - <span data-ttu-id="56e62-122">**FQDN do servidor de destino** Selecione a ID de serviço do serviço de Aplicativo que executa o aplicativo Comunicado que lidará com chamadas de entrada para esse intervalo de números não atribuídos.</span><span class="sxs-lookup"><span data-stu-id="56e62-122">**FQDN of destination server** Select the service ID of the Application service that runs the Announcement application that will handle incoming calls to this range of unassigned numbers.</span></span>

  - <span data-ttu-id="56e62-123">**Comunicado** Selecione o comunicado a ser tocado para esse intervalo de números não atribuídos.</span><span class="sxs-lookup"><span data-stu-id="56e62-123">**Announcement** Select the announcement to be played for this range of unassigned numbers.</span></span>

- <span data-ttu-id="56e62-124">Se você tiver selecionado **U do Exchange** para **Serviço de anúncio**:</span><span class="sxs-lookup"><span data-stu-id="56e62-124">If you selected **Exchange UM** for **Announcement service**:</span></span>

  - <span data-ttu-id="56e62-125">**Número de telefone do Atendente Automático** Selecione o número de telefone para o Atendente Automático de UM do Exchange.</span><span class="sxs-lookup"><span data-stu-id="56e62-125">**Auto Attendant phone number** Select the phone number for the Exchange UM Auto Attendant.</span></span>

<span data-ttu-id="56e62-126">Para obter detalhes sobre os recursos de Comunicado, consulte [Plan for the Announcement application in Skype for Business 2015](../../plan-your-deployment/enterprise-voice-solution/announcement.md) na documentação planejamento.</span><span class="sxs-lookup"><span data-stu-id="56e62-126">For details about Announcement features and capabilities, see [Plan for the Announcement application in Skype for Business 2015](../../plan-your-deployment/enterprise-voice-solution/announcement.md) in the Planning documentation.</span></span> <span data-ttu-id="56e62-127">Para obter detalhes sobre como trabalhar com intervalos de números não atribuídos, consulte [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) na documentação Operações.</span><span class="sxs-lookup"><span data-stu-id="56e62-127">For details about working with unassigned number ranges, see [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) in the Operations documentation.</span></span>


