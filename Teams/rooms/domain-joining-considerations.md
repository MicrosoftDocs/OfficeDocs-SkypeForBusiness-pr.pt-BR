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
description: O administrador pode aprender sobre como ingressar um computador do Skype de dispositivos do Sistema de Sala a um domínio do Active Directory, juntamente com as considerações para fazer isso.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c322819fb765e05cead793c95b5e3b6af2d2a180
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117549"
---
<!-- This asset missed in the rebrand, and honestly not sure if it's worth keeping.   -->

# <a name="skype-room-system-domain-joining-considerations"></a><span data-ttu-id="2379a-103">Considerações de ingresso no domínio do Sistema de Salas do Skype</span><span class="sxs-lookup"><span data-stu-id="2379a-103">Skype Room System domain joining considerations</span></span>
 
<span data-ttu-id="2379a-104">Leia este tópico para saber como ingressar o PC do cliente do Sistema de Salas do Skype em seu domínio.</span><span class="sxs-lookup"><span data-stu-id="2379a-104">Read this topic to learn how to join a Skype Room System appliance PC to your domain.</span></span>
  
## <a name="domain-joining-considerations"></a><span data-ttu-id="2379a-105">Considerações de ingresso no Domínio</span><span class="sxs-lookup"><span data-stu-id="2379a-105">Domain joining considerations</span></span>

<span data-ttu-id="2379a-106">Você pode ingressar o computador Skype de dispositivo do Sistema de Sala ao domínio do Active Directory ou deixá-lo em um Grupo de Trabalho.</span><span class="sxs-lookup"><span data-stu-id="2379a-106">You can join the Skype Room System appliance PC to the Active Directory domain or leave it in a Workgroup.</span></span> <span data-ttu-id="2379a-107">Considere os seguintes pontos antes da tomada desta decisão:</span><span class="sxs-lookup"><span data-stu-id="2379a-107">Consider the following points before making this decision:</span></span>
  
- <span data-ttu-id="2379a-108">A junção de domínio ao computador do Skype do sistema de sala ajuda a importar automaticamente a cadeia de certificados raiz privada da sua organização.</span><span class="sxs-lookup"><span data-stu-id="2379a-108">Domain-joining the Skype Room System appliance PC helps in importing your organization's private root certificate chain automatically.</span></span>
- <span data-ttu-id="2379a-109">A junção de domínio ao computador Skype de dispositivo do Sistema de Sala permite conceder direitos administrativos a usuários de domínio e grupos.</span><span class="sxs-lookup"><span data-stu-id="2379a-109">Domain-joining the Skype Room System appliance PC enables you to grant domain users and groups administrative rights.</span></span> <span data-ttu-id="2379a-110">Ao fazer isso, você não precisará ter que se lembrar da senha da conta do administrador no nível da máquina local.</span><span class="sxs-lookup"><span data-stu-id="2379a-110">By doing so, you will not have to remember the local machine level administrator account password.</span></span>
- <span data-ttu-id="2379a-111">Quando você instala um computador de dispositivo do sistema de sala do Skype no domínio, é necessário criar uma UO (Unidade Organizacional) separada, para que você possa fornecer exclusões de Objeto de Política de Grupo (GPO) para a UO onde residem todos os objetos de máquina do Sistema de Salas do Skype.</span><span class="sxs-lookup"><span data-stu-id="2379a-111">When you join a Skype Room System appliance PC to the domain, it is required that you create a separate Organizational Unit (OU), so that you can provide Group Policy Object (GPO) exclusions to the OU where all the Skype Room System machine objects reside.</span></span> <span data-ttu-id="2379a-112">Ao fazer isso, crie objetos de máquina na UO antes de ingressar no computador de dispositivo do sistema de sala Skype ao domínio.</span><span class="sxs-lookup"><span data-stu-id="2379a-112">When you do this, create machine objects in the OU before joining the Skype Room System appliance PC to the domain.</span></span>
- <span data-ttu-id="2379a-113">Muitas organizações têm os seguintes GPOs, que afetam Skype funções de computador de dispositivo do Sistema de Sala.</span><span class="sxs-lookup"><span data-stu-id="2379a-113">Many organizations have the following GPOs, which affect Skype Room System appliance PC functions.</span></span> <span data-ttu-id="2379a-114">Certifique-se de substituir ou bloquear a herança desses GPOs na UO do sistema de sala Skype sala:</span><span class="sxs-lookup"><span data-stu-id="2379a-114">Ensure that you override or block the inheritance of these GPOs in the Skype Room System OU:</span></span>

  - <span data-ttu-id="2379a-115">Tempo limite de sessões de logon (bloqueio automático)</span><span class="sxs-lookup"><span data-stu-id="2379a-115">Timeout of logon sessions (auto lockout)</span></span>
  - <span data-ttu-id="2379a-116">Políticas relacionadas ao gerenciamento de energia</span><span class="sxs-lookup"><span data-stu-id="2379a-116">Policies related to power management</span></span>
  - <span data-ttu-id="2379a-117">Requerendo etapas adicionais de autenticação</span><span class="sxs-lookup"><span data-stu-id="2379a-117">Requiring additional authentication steps</span></span>
  - <span data-ttu-id="2379a-118">Negando acesso a unidades locais</span><span class="sxs-lookup"><span data-stu-id="2379a-118">Denying access to local drives</span></span>
  - <span data-ttu-id="2379a-119">Avisando usuários para conexões de rede lentas</span><span class="sxs-lookup"><span data-stu-id="2379a-119">Prompting users for slow network connections</span></span>
  - <span data-ttu-id="2379a-120">Iniciar um determinado programa no logon</span><span class="sxs-lookup"><span data-stu-id="2379a-120">Start a certain program at logon</span></span>
  - <span data-ttu-id="2379a-121">Crie uma outra conta de usuário de domínio em todas as máquinas que ingressaram no domínio.</span><span class="sxs-lookup"><span data-stu-id="2379a-121">Create another domain user account on all domain-joined machines.</span></span>
  - <span data-ttu-id="2379a-122">Push Windows Update to Skype Room System</span><span class="sxs-lookup"><span data-stu-id="2379a-122">Push Windows Update to Skype Room System</span></span>
    
- <span data-ttu-id="2379a-123">Opcionalmente, você pode optar por deixar o PC de cliente no grupo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="2379a-123">Alternatively, you might decide to leave the appliance PC in the workgroup.</span></span> <span data-ttu-id="2379a-124">Assim como com o cliente Microsoft Teams ou Skype for Business desktop, isso exige que você importe manualmente a cadeia de certificados raiz no computador do dispositivo Skype Room System.</span><span class="sxs-lookup"><span data-stu-id="2379a-124">As with the desktop Microsoft Teams or Skype for Business client, this requires you to manually import the root certificate chain on the Skype Room System appliance PC.</span></span> <span data-ttu-id="2379a-125">Não é necessário importar a cadeia de certificados raiz se sua implantação estiver usando um certificado público (por exemplo, Entrust, VeriSign e assim por diante).</span><span class="sxs-lookup"><span data-stu-id="2379a-125">You're not required to import the root certificate chain if your deployment is using a public certificate (for example, Entrust, VeriSign, and so on).</span></span> 
    
<span data-ttu-id="2379a-126">Se você planeja ingressar Skype máquinas do Sistema de Sala ao domínio, para evitar ingressar o computador do sistema de sala do Skype inadvertidamente em uma UO não intencional, que pode não estar livre de GPOs, certifique-se de ingressar na UO correta.</span><span class="sxs-lookup"><span data-stu-id="2379a-126">If you plan to join Skype Room System machines to the domain, to avoid joining Skype Room System machine inadvertently to an unintended OU, which may not be free from GPOs, please ensure you join the correct OU.</span></span> <span data-ttu-id="2379a-127">Você pode usar o cmdlet a seguir da máquina do sistema de sala Skype para ingressar na OU correta e não recebe GPOs que podem bloquear a funcionalidade LRS.</span><span class="sxs-lookup"><span data-stu-id="2379a-127">You can use the following cmdlet from the Skype Room System machine to join in the correct OU and does not receive GPOs that might block LRS functionality.</span></span> <span data-ttu-id="2379a-128">Entre em contato com o administrador do sistema ou com o parceiro OEM para executar esses cmdlets:</span><span class="sxs-lookup"><span data-stu-id="2379a-128">Contact your system administrator or OEM partner to run these cmdlets:</span></span>
  
```powershell
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

<span data-ttu-id="2379a-129">Mesmo que você crie uma UO separada e bloqueie a herança, existem algumas políticas que podem causar problemas em um nível superior.</span><span class="sxs-lookup"><span data-stu-id="2379a-129">Even if you create a separate OU and block inheritance, there are some policies that could cause issues at a higher level.</span></span> <span data-ttu-id="2379a-130">A configuração Política de Grupo sem Substituição supera uma UO com uma configuração Bloquear Herança de Política.</span><span class="sxs-lookup"><span data-stu-id="2379a-130">A Group Policy with No Override setting beats an OU with a Block Policy Inheritance setting.</span></span> <span data-ttu-id="2379a-131">Para obter mais informações, consulte [No Override as Compared to Block Policy Inheritance](/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) na documentação da Política de Grupo.</span><span class="sxs-lookup"><span data-stu-id="2379a-131">For more information, see [No Override as Compared to Block Policy Inheritance](/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) in the Group Policy documentation.</span></span>
  
<span data-ttu-id="2379a-132">Você pode ter várias abordagens para resolver esses problemas.</span><span class="sxs-lookup"><span data-stu-id="2379a-132">You may have multiple approaches to solving these problems.</span></span> <span data-ttu-id="2379a-133">Recomendamos que você consulte seus especialistas do Active Directory para garantir que você tenha uma OU que tenha configurações de GPO apropriadas ou pelo menos uma UO na qual as políticas descritas anteriormente não existem.</span><span class="sxs-lookup"><span data-stu-id="2379a-133">We advise you to consult with your Active Directory experts to ensure that you are provided with an OU that has appropriate GPO settings, or at least an OU in which the previously described policies do not exist.</span></span> <span data-ttu-id="2379a-134">Recomendamos a habilitação de QoS (Qualidade de Serviço) para dispositivos Skype Room System.</span><span class="sxs-lookup"><span data-stu-id="2379a-134">We advise to enabling Quality of Service (QoS) for Skype Room System devices.</span></span>

## <a name="related-topics"></a><span data-ttu-id="2379a-135">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="2379a-135">Related topics</span></span>
  
[<span data-ttu-id="2379a-136">Configuração de Dispositivo: Criar Nova ou Editar Existente</span><span class="sxs-lookup"><span data-stu-id="2379a-136">Device Configuration: Create New or Edit Existing</span></span>](/skypeforbusiness/help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[<span data-ttu-id="2379a-137">Gerenciando a Qualidade de Serviço</span><span class="sxs-lookup"><span data-stu-id="2379a-137">Managing Quality of Service</span></span>](/skypeforbusiness/plan-your-deployment/network-requirements/network-requirements#managing-quality-of-service)