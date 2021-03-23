---
title: Considerações de ingresso no domínio do Sistema de Salas do Skype
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3034fdcb-7c89-42c4-9c5e-13400e82d88f
ms.collection:
- M365-collaboration
description: O administrador pode aprender sobre como ingressar um computador de dispositivo do Sistema de Sala do Skype a um domínio do Active Directory, juntamente com as considerações para fazer isso.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 806dcac8f73f555227c03f7612f30fe4a598812f
ms.sourcegitcommit: 2eaf80bca6dfad367283e57662d81a809c9437e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/22/2021
ms.locfileid: "50997409"
---
<!-- This asset missed in the rebrand, and honestly not sure if it's worth keeping.   -->

# <a name="skype-room-system-domain-joining-considerations"></a><span data-ttu-id="1265e-103">Considerações de ingresso no domínio do Sistema de Salas do Skype</span><span class="sxs-lookup"><span data-stu-id="1265e-103">Skype Room System domain joining considerations</span></span>
 
<span data-ttu-id="1265e-104">Leia este tópico para saber como ingressar o PC do cliente do Sistema de Salas do Skype em seu domínio.</span><span class="sxs-lookup"><span data-stu-id="1265e-104">Read this topic to learn how to join a Skype Room System appliance PC to your domain.</span></span>
  
## <a name="domain-joining-considerations"></a><span data-ttu-id="1265e-105">Considerações de ingresso no Domínio</span><span class="sxs-lookup"><span data-stu-id="1265e-105">Domain joining considerations</span></span>

<span data-ttu-id="1265e-106">Você pode ingressar o computador de dispositivo do Sistema de Sala do Skype no domínio do Active Directory ou deixá-lo em um Grupo de Trabalho.</span><span class="sxs-lookup"><span data-stu-id="1265e-106">You can join the Skype Room System appliance PC to the Active Directory domain or leave it in a Workgroup.</span></span> <span data-ttu-id="1265e-107">Considere os seguintes pontos antes da tomada desta decisão:</span><span class="sxs-lookup"><span data-stu-id="1265e-107">Consider the following points before making this decision:</span></span>
  
- <span data-ttu-id="1265e-108">A junção de domínio ao computador de dispositivo do Sistema de Sala do Skype ajuda a importar automaticamente a cadeia de certificados raiz privada da sua organização.</span><span class="sxs-lookup"><span data-stu-id="1265e-108">Domain-joining the Skype Room System appliance PC helps in importing your organization's private root certificate chain automatically.</span></span>
- <span data-ttu-id="1265e-109">A junção de domínio ao computador de dispositivo do Sistema de Sala do Skype permite que você conceda direitos administrativos a usuários e grupos de domínio.</span><span class="sxs-lookup"><span data-stu-id="1265e-109">Domain-joining the Skype Room System appliance PC enables you to grant domain users and groups administrative rights.</span></span> <span data-ttu-id="1265e-110">Ao fazer isso, você não precisará ter que se lembrar da senha da conta do administrador no nível da máquina local.</span><span class="sxs-lookup"><span data-stu-id="1265e-110">By doing so, you will not have to remember the local machine level administrator account password.</span></span>
- <span data-ttu-id="1265e-111">Ao ingressar em um computador de dispositivo do Sistema de Sala do Skype no domínio, é necessário criar uma Unidade Organizacional (OU) separada, para que você possa fornecer exclusões de OBJETO de Política de Grupo (GPO) para a UO onde todos os objetos de máquina do Sistema de Sala do Skype residem.</span><span class="sxs-lookup"><span data-stu-id="1265e-111">When you join a Skype Room System appliance PC to the domain, it is required that you create a separate Organizational Unit (OU), so that you can provide Group Policy Object (GPO) exclusions to the OU where all the Skype Room System machine objects reside.</span></span> <span data-ttu-id="1265e-112">Ao fazer isso, crie objetos de máquina na UO antes de ingressar no computador de dispositivo do Sistema de Sala do Skype no domínio.</span><span class="sxs-lookup"><span data-stu-id="1265e-112">When you do this, create machine objects in the OU before joining the Skype Room System appliance PC to the domain.</span></span>
- <span data-ttu-id="1265e-113">Muitas organizações têm os seguintes GPOs, que afetam as funções de computador do dispositivo do Sistema de Sala do Skype.</span><span class="sxs-lookup"><span data-stu-id="1265e-113">Many organizations have the following GPOs, which affect Skype Room System appliance PC functions.</span></span> <span data-ttu-id="1265e-114">Verifique se você substitui ou bloqueia a herança desses GPOs na UO do Sistema de Sala do Skype:</span><span class="sxs-lookup"><span data-stu-id="1265e-114">Ensure that you override or block the inheritance of these GPOs in the Skype Room System OU:</span></span>

  - <span data-ttu-id="1265e-115">Tempo limite de sessões de logon (bloqueio automático)</span><span class="sxs-lookup"><span data-stu-id="1265e-115">Timeout of logon sessions (auto lockout)</span></span>
  - <span data-ttu-id="1265e-116">Políticas relacionadas ao gerenciamento de energia</span><span class="sxs-lookup"><span data-stu-id="1265e-116">Policies related to power management</span></span>
  - <span data-ttu-id="1265e-117">Requerendo etapas adicionais de autenticação</span><span class="sxs-lookup"><span data-stu-id="1265e-117">Requiring additional authentication steps</span></span>
  - <span data-ttu-id="1265e-118">Negando acesso a unidades locais</span><span class="sxs-lookup"><span data-stu-id="1265e-118">Denying access to local drives</span></span>
  - <span data-ttu-id="1265e-119">Avisando usuários para conexões de rede lentas</span><span class="sxs-lookup"><span data-stu-id="1265e-119">Prompting users for slow network connections</span></span>
  - <span data-ttu-id="1265e-120">Iniciar um determinado programa no logon</span><span class="sxs-lookup"><span data-stu-id="1265e-120">Start a certain program at logon</span></span>
  - <span data-ttu-id="1265e-121">Crie uma outra conta de usuário de domínio em todas as máquinas que ingressaram no domínio.</span><span class="sxs-lookup"><span data-stu-id="1265e-121">Create another domain user account on all domain-joined machines.</span></span>
  - <span data-ttu-id="1265e-122">Push Windows Update to Skype Room System</span><span class="sxs-lookup"><span data-stu-id="1265e-122">Push Windows Update to Skype Room System</span></span>
    
- <span data-ttu-id="1265e-123">Opcionalmente, você pode optar por deixar o PC de cliente no grupo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="1265e-123">Alternatively, you might decide to leave the appliance PC in the workgroup.</span></span> <span data-ttu-id="1265e-124">Assim como no microsoft teams da área de trabalho ou cliente do Skype for Business, isso exige que você importe manualmente a cadeia de certificados raiz no computador de dispositivo do Sistema de Sala do Skype.</span><span class="sxs-lookup"><span data-stu-id="1265e-124">As with the desktop Microsoft Teams or Skype for Business client, this requires you to manually import the root certificate chain on the Skype Room System appliance PC.</span></span> <span data-ttu-id="1265e-125">Não é necessário importar a cadeia de certificados raiz se sua implantação estiver usando um certificado público (por exemplo, Entrust, VeriSign e assim por diante).</span><span class="sxs-lookup"><span data-stu-id="1265e-125">You're not required to import the root certificate chain if your deployment is using a public certificate (for example, Entrust, VeriSign, and so on).</span></span> 
    
<span data-ttu-id="1265e-126">Se você planeja ingressar máquinas do Sistema de Sala do Skype no domínio, para evitar ingressar a máquina do Sistema de Sala do Skype inadvertidamente em uma UO não intencional, que pode não estar livre de GPOs, certifique-se de ingressar na OU correta.</span><span class="sxs-lookup"><span data-stu-id="1265e-126">If you plan to join Skype Room System machines to the domain, to avoid joining Skype Room System machine inadvertently to an unintended OU, which may not be free from GPOs, please ensure you join the correct OU.</span></span> <span data-ttu-id="1265e-127">Você pode usar o seguinte cmdlet da máquina do Sistema de Sala do Skype para ingressar na OU correta e não recebe GPOs que podem bloquear a funcionalidade LRS.</span><span class="sxs-lookup"><span data-stu-id="1265e-127">You can use the following cmdlet from the Skype Room System machine to join in the correct OU and does not receive GPOs that might block LRS functionality.</span></span> <span data-ttu-id="1265e-128">Entre em contato com o administrador do sistema ou com o parceiro OEM para executar esses cmdlets:</span><span class="sxs-lookup"><span data-stu-id="1265e-128">Contact your system administrator or OEM partner to run these cmdlets:</span></span>
  
```powershell
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

<span data-ttu-id="1265e-129">Mesmo que você crie uma UO separada e bloqueie a herança, existem algumas políticas que podem causar problemas em um nível superior.</span><span class="sxs-lookup"><span data-stu-id="1265e-129">Even if you create a separate OU and block inheritance, there are some policies that could cause issues at a higher level.</span></span> <span data-ttu-id="1265e-130">A configuração Política de Grupo sem Substituição supera uma UO com uma configuração Bloquear Herança de Política.</span><span class="sxs-lookup"><span data-stu-id="1265e-130">A Group Policy with No Override setting beats an OU with a Block Policy Inheritance setting.</span></span> <span data-ttu-id="1265e-131">Para obter mais informações, consulte [No Override as Compared to Block Policy Inheritance](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) na documentação da Política de Grupo.</span><span class="sxs-lookup"><span data-stu-id="1265e-131">For more information, see [No Override as Compared to Block Policy Inheritance](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) in the Group Policy documentation.</span></span>
  
<span data-ttu-id="1265e-132">Você pode ter várias abordagens para resolver esses problemas.</span><span class="sxs-lookup"><span data-stu-id="1265e-132">You may have multiple approaches to solving these problems.</span></span> <span data-ttu-id="1265e-133">Recomendamos que você consulte seus especialistas do Active Directory para garantir que você tenha uma OU que tenha configurações de GPO apropriadas ou pelo menos uma UO na qual as políticas descritas anteriormente não existem.</span><span class="sxs-lookup"><span data-stu-id="1265e-133">We advise you to consult with your Active Directory experts to ensure that you are provided with an OU that has appropriate GPO settings, or at least an OU in which the previously described policies do not exist.</span></span> <span data-ttu-id="1265e-134">Recomendamos a habilitação de QoS (Qualidade de Serviço) para dispositivos do Sistema de Sala do Skype.</span><span class="sxs-lookup"><span data-stu-id="1265e-134">We advise to enabling Quality of Service (QoS) for Skype Room System devices.</span></span>

## <a name="related-topics"></a><span data-ttu-id="1265e-135">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="1265e-135">Related topics</span></span>
  
[<span data-ttu-id="1265e-136">Configuração de Dispositivo: Criar Nova ou Editar Existente</span><span class="sxs-lookup"><span data-stu-id="1265e-136">Device Configuration: Create New or Edit Existing</span></span>](/skypeforbusiness/help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[<span data-ttu-id="1265e-137">Gerenciando a Qualidade de Serviço</span><span class="sxs-lookup"><span data-stu-id="1265e-137">Managing Quality of Service</span></span>](/skypeforbusiness/plan-your-deployment/network-requirements/network-requirements#managing-quality-of-service)
