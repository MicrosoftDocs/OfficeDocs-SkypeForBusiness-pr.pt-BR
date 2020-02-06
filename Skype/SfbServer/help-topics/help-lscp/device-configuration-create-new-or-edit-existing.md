---
title: Configuração do dispositivo criar novo ou editar existente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientPhoneCfgEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aac152bf-80e9-408a-9dbb-60d0843484ab
description: Na página configuração do novo dispositivo ou editar configuração do dispositivo, você pode criar ou modificar um conjunto de configurações usadas para gerenciar o Skype for Business Phone Edition. Essas configurações permitem que você configure aspectos como o modo de segurança necessário, o nível de log do dispositivo, as configurações de QoS (Qualidade de voz do serviço) e se os telefones devem ser bloqueados automaticamente após um período especificado de inatividade.
ms.openlocfilehash: 95ce62b5d3505e10049d61ead77ce79ee7f2f51b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41822924"
---
# <a name="device-configuration-create-new-or-edit-existing"></a><span data-ttu-id="d04c8-104">Configuração de Dispositivo: Criar Nova ou Editar Existente</span><span class="sxs-lookup"><span data-stu-id="d04c8-104">Device Configuration: Create New or Edit Existing</span></span>
 
<span data-ttu-id="d04c8-105">Na página **configuração do novo dispositivo** ou **Editar configuração do dispositivo** , você pode criar ou modificar um conjunto de configurações usadas para gerenciar o Skype for Business Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="d04c8-105">On the **New Device Configuration** or **Edit Device Configuration** page, you can create or modify a collection of settings used to manage Skype for Business Phone Edition.</span></span> <span data-ttu-id="d04c8-106">Essas configurações permitem que você configure aspectos como o modo de segurança necessário, o nível de log do dispositivo, as configurações de QoS (Qualidade de voz do serviço) e se os telefones devem ser bloqueados automaticamente após um período especificado de inatividade.</span><span class="sxs-lookup"><span data-stu-id="d04c8-106">These settings enable you to configure such things as the required security mode, device logging level, Voice Quality of Service (QoS) settings, and whether or not phones should automatically lock after a specified period of inactivity.</span></span>
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="d04c8-107">Tarefas que podem ser executadas</span><span class="sxs-lookup"><span data-stu-id="d04c8-107">Tasks you can perform</span></span>

<span data-ttu-id="d04c8-108">É possível executar as seguintes tarefas na página **Nova Configuração de Dispositivo** ou  **Editar Configuração de Dispositivo**:</span><span class="sxs-lookup"><span data-stu-id="d04c8-108">You can perform the following tasks on the **New Device Configuration** or **Edit Device Configuration** page:</span></span>
  
- <span data-ttu-id="d04c8-109">Adicionar uma nova configuração de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d04c8-109">Add a new device configuration.</span></span>
    
- <span data-ttu-id="d04c8-110">Modificar as propriedades de uma configuração de dispositivo existente.</span><span class="sxs-lookup"><span data-stu-id="d04c8-110">Modify the properties of an existing device configuration.</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="d04c8-111">Referência de UI</span><span class="sxs-lookup"><span data-stu-id="d04c8-111">UI Reference</span></span>

<span data-ttu-id="d04c8-112">As listas a seguir descrevem os menus, comandos, campos e propriedades na página.</span><span class="sxs-lookup"><span data-stu-id="d04c8-112">The following lists describe the menus, commands, fields, and properties on the page.</span></span>
  
- <span data-ttu-id="d04c8-113">**Escopo** Identifica o escopo (global ou site) da configuração do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d04c8-113">**Scope** Identifies the scope (Global or Site) of the device configuration.</span></span>
    
- <span data-ttu-id="d04c8-114">**Nome** Você pode adicionar ou modificar o nome da configuração do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d04c8-114">**Name** You can add or modify the name of the device configuration.</span></span>
    
- <span data-ttu-id="d04c8-115">**Segurança SIP** Você pode configurar requisitos de transporte e autenticação para dispositivos do Skype for Business Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="d04c8-115">**SIP security** You can configure transport and authentication requirements for Skype for Business Phone Edition devices.</span></span> <span data-ttu-id="d04c8-116">É possível selecionar dentre as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="d04c8-116">You can select from the following options:</span></span>
    
  - <span data-ttu-id="d04c8-117">**Baixo** Permitir qualquer tipo de autorização ou transporte.</span><span class="sxs-lookup"><span data-stu-id="d04c8-117">**Low** Allow any type of authorization or transport.</span></span>
    
  - <span data-ttu-id="d04c8-118">**Média** NTLM ou Kerberos é necessário para autenticação do usuário.</span><span class="sxs-lookup"><span data-stu-id="d04c8-118">**Medium** NTLM or Kerberos is required for user authentication.</span></span>
    
  - <span data-ttu-id="d04c8-119">**Alta** NTLM ou Kerberos é necessário para a autenticação do usuário e o TLS é necessário para conexões SIP.</span><span class="sxs-lookup"><span data-stu-id="d04c8-119">**High** NTLM or Kerberos is required for user authentication and TLS is required for SIP connections.</span></span>
    
- <span data-ttu-id="d04c8-120">**Nível de log** Você pode habilitar o registro em log no dispositivo de comunicação unificada.</span><span class="sxs-lookup"><span data-stu-id="d04c8-120">**Logging level** You can enable logging on the UC device.</span></span> <span data-ttu-id="d04c8-121">Os valores válidos são: Desativado; Baixo; Médio; e Alto.</span><span class="sxs-lookup"><span data-stu-id="d04c8-121">Valid values are: Off; Low; Medium; and High.</span></span> <span data-ttu-id="d04c8-122">O valor padrão é Desativado.</span><span class="sxs-lookup"><span data-stu-id="d04c8-122">The default value is Off.</span></span>
    
- <span data-ttu-id="d04c8-123">**Qualidade de serviço (QoS) de voz** Você pode especificar o valor de DSCP atribuído a um tráfego de voz que emana de um dispositivo Skype for Business Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="d04c8-123">**Voice Quality of Service (QoS)** You can specify the DSCP value assigned to voice traffic emanating from a Skype for Business Phone Edition device.</span></span> <span data-ttu-id="d04c8-124">O padrão é 40.</span><span class="sxs-lookup"><span data-stu-id="d04c8-124">The default is 40.</span></span> <span data-ttu-id="d04c8-125">No entanto, 40 não é o valor normalmente usado para tráfego de áudio; em vez disso, o tráfego de áudio é quase sempre marcado com o código DSCP 46.</span><span class="sxs-lookup"><span data-stu-id="d04c8-125">However, 40 is not the value typically used for audio traffic; instead, audio traffic is almost always marked with the DSCP code 46.</span></span> <span data-ttu-id="d04c8-126">Para manter a consistência em toda sua rede, convém alterar esse valor para 46.</span><span class="sxs-lookup"><span data-stu-id="d04c8-126">In order to maintain consistency throughout your network, you might want to change this value to 46.</span></span>
    
- <span data-ttu-id="d04c8-127">**Bloqueio de telefone** Você pode especificar se os telefones UC serão bloqueados automaticamente após um período de inatividade especificado.</span><span class="sxs-lookup"><span data-stu-id="d04c8-127">**Phone lock** You can specify whether or not UC phones will automatically lock themselves after a specified period of inactivity.</span></span> <span data-ttu-id="d04c8-128">Veja a seguir as configurações possíveis:</span><span class="sxs-lookup"><span data-stu-id="d04c8-128">The following are the settings you can configure:</span></span>
    
  - <span data-ttu-id="d04c8-129">**Impor o bloqueio de dispositivo** Você pode impor o bloqueio do dispositivo marcando essa caixa de seleção.</span><span class="sxs-lookup"><span data-stu-id="d04c8-129">**Enforce device locking** You can enforce device locking by selecting this check box.</span></span>
    
  - <span data-ttu-id="d04c8-130">**Comprimento mínimo do PIN** Você pode especificar o comprimento mínimo para o número de identificação pessoal (PIN) que é usado para desbloquear o telefone.</span><span class="sxs-lookup"><span data-stu-id="d04c8-130">**Minimum PIN length** You can specify the minimum length for the personal identification number (PIN) that is used to unlock the phone.</span></span> <span data-ttu-id="d04c8-131">O tamanho do PIN é de quatro a 15 dígitos.</span><span class="sxs-lookup"><span data-stu-id="d04c8-131">The range for the PIN length is four to 15 digits.</span></span> <span data-ttu-id="d04c8-132">O tamanho padrão é de seis dígitos.</span><span class="sxs-lookup"><span data-stu-id="d04c8-132">The default length is six digits.</span></span>
    
  - <span data-ttu-id="d04c8-133">**Tempo limite de bloqueio de telefone** Você pode especificar o período mínimo de tempo até que o telefone seja bloqueado.</span><span class="sxs-lookup"><span data-stu-id="d04c8-133">**Phone lock time-out** You can specify the minimum length of time before the phone locks itself.</span></span> <span data-ttu-id="d04c8-134">O intervalo para o tempo limite é de 0 a 60 minutos; o valor padrão é de 10 minutos.</span><span class="sxs-lookup"><span data-stu-id="d04c8-134">The range for the time-out is 0 to 60 minutes; the default value is 10 minutes.</span></span> <span data-ttu-id="d04c8-135">Insira o valor no formato HH:MM:SS.</span><span class="sxs-lookup"><span data-stu-id="d04c8-135">Enter the value in the format HH:MM:SS.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="d04c8-136">Confira também</span><span class="sxs-lookup"><span data-stu-id="d04c8-136">See also</span></span>

[<span data-ttu-id="d04c8-137">Configuração do dispositivo</span><span class="sxs-lookup"><span data-stu-id="d04c8-137">Device Configuration</span></span>](device-configuration.md)

[<span data-ttu-id="d04c8-138">Set-CsUCPhoneConfiguration</span><span class="sxs-lookup"><span data-stu-id="d04c8-138">Set-CsUCPhoneConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps)
