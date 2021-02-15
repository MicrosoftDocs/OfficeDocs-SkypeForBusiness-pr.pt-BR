---
title: Configuração do Dispositivo Criar Nova ou Editar Existente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientPhoneCfgEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: aac152bf-80e9-408a-9dbb-60d0843484ab
ROBOTS: NOINDEX, NOFOLLOW
description: Na página Nova Configuração de Dispositivo ou Editar Configuração de Dispositivo, você pode criar ou modificar uma coleção de configurações usadas para gerenciar o Skype for Business Phone Edition. Essas configurações permitem que você configure coisas como o modo de segurança necessário, o nível de log do dispositivo, as configurações de QoS (Qualidade de voz do serviço) e se os telefones devem ser bloqueados automaticamente após um período especificado de inatividade.
ms.openlocfilehash: 0b330212c8dc050bb618f28ea6444b1c8e58f040
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830191"
---
# <a name="device-configuration-create-new-or-edit-existing"></a><span data-ttu-id="81859-104">Configuração de Dispositivo: Criar Nova ou Editar Existente</span><span class="sxs-lookup"><span data-stu-id="81859-104">Device Configuration: Create New or Edit Existing</span></span>
 
<span data-ttu-id="81859-105">Na página **Nova Configuração de** Dispositivo ou Editar Configuração **de** Dispositivo, você pode criar ou modificar uma coleção de configurações usadas para gerenciar o Skype for Business Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="81859-105">On the **New Device Configuration** or **Edit Device Configuration** page, you can create or modify a collection of settings used to manage Skype for Business Phone Edition.</span></span> <span data-ttu-id="81859-106">Essas configurações permitem que você configure coisas como o modo de segurança necessário, o nível de log do dispositivo, as configurações de QoS (Qualidade de voz do serviço) e se os telefones devem ser bloqueados automaticamente após um período especificado de inatividade.</span><span class="sxs-lookup"><span data-stu-id="81859-106">These settings enable you to configure such things as the required security mode, device logging level, Voice Quality of Service (QoS) settings, and whether or not phones should automatically lock after a specified period of inactivity.</span></span>
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="81859-107">Tarefas que podem ser executadas</span><span class="sxs-lookup"><span data-stu-id="81859-107">Tasks you can perform</span></span>

<span data-ttu-id="81859-108">É possível executar as seguintes tarefas na página **Nova Configuração de Dispositivo** ou **Editar Configuração de Dispositivo**:</span><span class="sxs-lookup"><span data-stu-id="81859-108">You can perform the following tasks on the **New Device Configuration** or **Edit Device Configuration** page:</span></span>
  
- <span data-ttu-id="81859-109">Adicionar uma nova configuração de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="81859-109">Add a new device configuration.</span></span>
    
- <span data-ttu-id="81859-110">Modificar as propriedades de uma configuração de dispositivo existente.</span><span class="sxs-lookup"><span data-stu-id="81859-110">Modify the properties of an existing device configuration.</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="81859-111">Referência de UI</span><span class="sxs-lookup"><span data-stu-id="81859-111">UI Reference</span></span>

<span data-ttu-id="81859-112">As listas a seguir descrevem os menus, comandos, campos e propriedades na página.</span><span class="sxs-lookup"><span data-stu-id="81859-112">The following lists describe the menus, commands, fields, and properties on the page.</span></span>
  
- <span data-ttu-id="81859-113">**Escopo** Identifica o escopo (Global ou Site) da configuração do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="81859-113">**Scope** Identifies the scope (Global or Site) of the device configuration.</span></span>
    
- <span data-ttu-id="81859-114">**Nome** Você pode adicionar ou modificar o nome da configuração do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="81859-114">**Name** You can add or modify the name of the device configuration.</span></span>
    
- <span data-ttu-id="81859-115">**Segurança SIP** Você pode configurar os requisitos de transporte e autenticação para dispositivos Skype for Business Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="81859-115">**SIP security** You can configure transport and authentication requirements for Skype for Business Phone Edition devices.</span></span> <span data-ttu-id="81859-116">É possível selecionar dentre as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="81859-116">You can select from the following options:</span></span>
    
  - <span data-ttu-id="81859-117">**Baixo** Permitir qualquer tipo de autorização ou transporte.</span><span class="sxs-lookup"><span data-stu-id="81859-117">**Low** Allow any type of authorization or transport.</span></span>
    
  - <span data-ttu-id="81859-118">**Médio** NTLM ou Kerberos é necessário para autenticação do usuário.</span><span class="sxs-lookup"><span data-stu-id="81859-118">**Medium** NTLM or Kerberos is required for user authentication.</span></span>
    
  - <span data-ttu-id="81859-119">**Alto** NTLM ou Kerberos é necessário para autenticação do usuário e TLS é necessário para conexões SIP.</span><span class="sxs-lookup"><span data-stu-id="81859-119">**High** NTLM or Kerberos is required for user authentication and TLS is required for SIP connections.</span></span>
    
- <span data-ttu-id="81859-120">**Nível de log** Você pode habilitar o registro em log no dispositivo UC.</span><span class="sxs-lookup"><span data-stu-id="81859-120">**Logging level** You can enable logging on the UC device.</span></span> <span data-ttu-id="81859-121">Os valores válidos são: Desativado; Baixo; Médio; e Alto.</span><span class="sxs-lookup"><span data-stu-id="81859-121">Valid values are: Off; Low; Medium; and High.</span></span> <span data-ttu-id="81859-122">O valor padrão é Desativado.</span><span class="sxs-lookup"><span data-stu-id="81859-122">The default value is Off.</span></span>
    
- <span data-ttu-id="81859-123">**QoS (Qualidade de Serviço de Voz)** Você pode especificar o valor DSCP atribuído ao tráfego de voz que emana de um dispositivo Skype for Business Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="81859-123">**Voice Quality of Service (QoS)** You can specify the DSCP value assigned to voice traffic emanating from a Skype for Business Phone Edition device.</span></span> <span data-ttu-id="81859-124">O padrão é 40.</span><span class="sxs-lookup"><span data-stu-id="81859-124">The default is 40.</span></span> <span data-ttu-id="81859-125">No entanto, 40 não é o valor normalmente usado para tráfego de áudio; em vez disso, o tráfego de áudio é quase sempre marcado com o código DSCP 46.</span><span class="sxs-lookup"><span data-stu-id="81859-125">However, 40 is not the value typically used for audio traffic; instead, audio traffic is almost always marked with the DSCP code 46.</span></span> <span data-ttu-id="81859-126">Para manter a consistência em toda sua rede, convém alterar esse valor para 46.</span><span class="sxs-lookup"><span data-stu-id="81859-126">In order to maintain consistency throughout your network, you might want to change this value to 46.</span></span>
    
- <span data-ttu-id="81859-127">**Bloqueio de telefone** Você pode especificar se os telefones UC se bloquearão automaticamente após um período especificado de inatividade.</span><span class="sxs-lookup"><span data-stu-id="81859-127">**Phone lock** You can specify whether or not UC phones will automatically lock themselves after a specified period of inactivity.</span></span> <span data-ttu-id="81859-128">Veja a seguir as configurações possíveis:</span><span class="sxs-lookup"><span data-stu-id="81859-128">The following are the settings you can configure:</span></span>
    
  - <span data-ttu-id="81859-129">**Impor bloqueio de dispositivo** Você pode impor o bloqueio de dispositivo selecionando essa caixa de seleção.</span><span class="sxs-lookup"><span data-stu-id="81859-129">**Enforce device locking** You can enforce device locking by selecting this check box.</span></span>
    
  - <span data-ttu-id="81859-130">**Tamanho mínimo do PIN** Você pode especificar o tamanho mínimo do PIN (número de identificação pessoal) usado para desbloquear o telefone.</span><span class="sxs-lookup"><span data-stu-id="81859-130">**Minimum PIN length** You can specify the minimum length for the personal identification number (PIN) that is used to unlock the phone.</span></span> <span data-ttu-id="81859-131">O intervalo do tamanho do PIN é 4 a 15 dígitos.</span><span class="sxs-lookup"><span data-stu-id="81859-131">The range for the PIN length is four to 15 digits.</span></span> <span data-ttu-id="81859-132">O tamanho padrão é 6 dígitos..</span><span class="sxs-lookup"><span data-stu-id="81859-132">The default length is six digits.</span></span>
    
  - <span data-ttu-id="81859-133">**Tempo de bloqueio do telefone** Você pode especificar o período mínimo de tempo antes que o telefone se bloclua.</span><span class="sxs-lookup"><span data-stu-id="81859-133">**Phone lock time-out** You can specify the minimum length of time before the phone locks itself.</span></span> <span data-ttu-id="81859-134">O intervalo do tempo limite é 0 a 60 minutos; o valor padrão é 10 minutos.</span><span class="sxs-lookup"><span data-stu-id="81859-134">The range for the time-out is 0 to 60 minutes; the default value is 10 minutes.</span></span> <span data-ttu-id="81859-135">Insira o valor no formato HH:MM:SS.</span><span class="sxs-lookup"><span data-stu-id="81859-135">Enter the value in the format HH:MM:SS.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="81859-136">Confira também</span><span class="sxs-lookup"><span data-stu-id="81859-136">See also</span></span>

[<span data-ttu-id="81859-137">Configuração do dispositivo</span><span class="sxs-lookup"><span data-stu-id="81859-137">Device Configuration</span></span>](ms.lync.lscp.ClientDeviceCfgMain.md)

[<span data-ttu-id="81859-138">Set-CsUCPhoneConfiguration</span><span class="sxs-lookup"><span data-stu-id="81859-138">Set-CsUCPhoneConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps)
