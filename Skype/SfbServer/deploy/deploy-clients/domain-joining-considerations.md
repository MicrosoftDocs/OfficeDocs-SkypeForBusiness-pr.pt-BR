---
title: Considerações sobre como ingressar no domínio do Sistema de Sala do Skype
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3034fdcb-7c89-42c4-9c5e-13400e82d88f
description: Leia este tópico para saber como ingressar um PC do dispositivo do Sistema de Sala do Skype em seu domínio.
ms.openlocfilehash: 6d6decf689b1a38615851911b42676050a823e4d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805911"
---
# <a name="skype-room-system-domain-joining-considerations"></a><span data-ttu-id="c64db-103">Considerações sobre como ingressar no domínio do Sistema de Sala do Skype</span><span class="sxs-lookup"><span data-stu-id="c64db-103">Skype Room System domain joining considerations</span></span>
 
<span data-ttu-id="c64db-104">Leia este tópico para saber como ingressar um PC do dispositivo do Sistema de Sala do Skype em seu domínio.</span><span class="sxs-lookup"><span data-stu-id="c64db-104">Read this topic to learn how to join a Skype Room System appliance PC to your domain.</span></span>
  
## <a name="domain-joining-considerations"></a><span data-ttu-id="c64db-105">Considerações de associação de domínio</span><span class="sxs-lookup"><span data-stu-id="c64db-105">Domain joining considerations</span></span>

<span data-ttu-id="c64db-106">Você pode ingressar o PC do dispositivo do Sistema de Sala do Skype no domínio do Active Directory ou deixá-lo em um Grupo de Trabalho.</span><span class="sxs-lookup"><span data-stu-id="c64db-106">You can join the Skype Room System appliance PC to the Active Directory domain or leave it in a Workgroup.</span></span> <span data-ttu-id="c64db-107">Considere os seguintes pontos antes de tomar essa decisão:</span><span class="sxs-lookup"><span data-stu-id="c64db-107">Consider the following points before making this decision:</span></span>
  
- <span data-ttu-id="c64db-108">Ingressar no domínio do PC do dispositivo do Sistema de Sala do Skype ajuda a importar automaticamente a cadeia de certificado raiz privada da sua organização.</span><span class="sxs-lookup"><span data-stu-id="c64db-108">Domain-joining the Skype Room System appliance PC helps in importing your organization's private root certificate chain automatically.</span></span>
    
- <span data-ttu-id="c64db-109">Ingressar no domínio do PC do dispositivo do Sistema de Sala do Skype permite conceder direitos administrativos a usuários de domínio e grupos.</span><span class="sxs-lookup"><span data-stu-id="c64db-109">Domain-joining the Skype Room System appliance PC enables you to grant domain users and groups administrative rights.</span></span> <span data-ttu-id="c64db-110">Ao fazer isso, você não terá que se lembrar da senha da conta de administrador no nível do computador local.</span><span class="sxs-lookup"><span data-stu-id="c64db-110">By doing so, you will not have to remember the local machine level administrator account password.</span></span>
    
- <span data-ttu-id="c64db-111">Ao ingressar um PC de dispositivo do Sistema de Salas do Skype no domínio, é necessário criar uma Unidade Organizacional (UO) separada para que você possa fornecer exclusões de Objeto de Política de Grupo (GPO) para a UO onde residem todos os objetos da máquina do Sistema de Salas do Skype.</span><span class="sxs-lookup"><span data-stu-id="c64db-111">When you join an Skype Room System appliance PC to the domain, it is required that you create a separate Organizational Unit (OU), so that you can provide Group Policy Object (GPO) exclusions to the OU where all the Skype Room System machine objects reside.</span></span> <span data-ttu-id="c64db-112">Ao fazer isso, crie objetos de máquina na UO antes de ingressar o PC do dispositivo do Sistema de Sala do Skype no domínio.</span><span class="sxs-lookup"><span data-stu-id="c64db-112">When you do this, create machine objects in the OU before joining the Skype Room System appliance PC to the domain.</span></span>
    
- <span data-ttu-id="c64db-113">Muitas organizações têm os seguintes GPOs, que afetam as funções do PC do dispositivo do Sistema de Sala do Skype.</span><span class="sxs-lookup"><span data-stu-id="c64db-113">Many organizations have the following GPOs, which affect Skype Room System appliance PC functions.</span></span> <span data-ttu-id="c64db-114">Substitua ou bloqueie a herança desses GPOs na UO do Sistema de Sala do Skype:</span><span class="sxs-lookup"><span data-stu-id="c64db-114">Ensure that you override or block the inheritance of these GPOs in the Skype Room System OU:</span></span> 
    
  - <span data-ttu-id="c64db-115">Tempo final das sessões de logon (bloqueio automático)</span><span class="sxs-lookup"><span data-stu-id="c64db-115">Timeout of logon sessions (auto lockout)</span></span>
    
  - <span data-ttu-id="c64db-116">Políticas relacionadas ao gerenciamento de energia</span><span class="sxs-lookup"><span data-stu-id="c64db-116">Power management related policies</span></span>
    
  - <span data-ttu-id="c64db-117">Exigir etapas adicionais de autenticação</span><span class="sxs-lookup"><span data-stu-id="c64db-117">Requiring additional authentication steps</span></span>
    
  - <span data-ttu-id="c64db-118">Negando o acesso a unidades locais</span><span class="sxs-lookup"><span data-stu-id="c64db-118">Denying access to local drives</span></span>
    
  - <span data-ttu-id="c64db-119">Solicitando aos usuários conexões de rede lentas</span><span class="sxs-lookup"><span data-stu-id="c64db-119">Prompting users for slow network connections</span></span>
    
  - <span data-ttu-id="c64db-120">Iniciar um determinado programa no logon</span><span class="sxs-lookup"><span data-stu-id="c64db-120">Start a certain program at logon</span></span>
    
  - <span data-ttu-id="c64db-121">Crie outra conta de usuário de domínio em todos os máquinas ingressas no domínio.</span><span class="sxs-lookup"><span data-stu-id="c64db-121">Create another domain user account on all domain-joined machines.</span></span>
    
  - <span data-ttu-id="c64db-122">Push Windows Update to Skype Room System</span><span class="sxs-lookup"><span data-stu-id="c64db-122">Push Windows Update to Skype Room System</span></span>
    
- <span data-ttu-id="c64db-123">Como alternativa, você pode optar por deixar o PC do dispositivo no grupo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="c64db-123">Alternatively, you might decide to leave the appliance PC in the workgroup.</span></span> <span data-ttu-id="c64db-124">Assim como no cliente do Skype for Business para área de trabalho, isso exige que você importe manualmente a cadeia de certificado raiz no PC do dispositivo do Sistema de Sala do Skype.</span><span class="sxs-lookup"><span data-stu-id="c64db-124">As with the desktop Skype for Business client, this requires you to manually import the root certificate chain on the Skype Room System appliance PC.</span></span> <span data-ttu-id="c64db-125">Você não é obrigado a importar a cadeia de certificado raiz se sua implantação do Skype for Business estiver usando um certificado público (por exemplo, DiadePondo, VeriSign e assim por diante).</span><span class="sxs-lookup"><span data-stu-id="c64db-125">You're not required to import the root certificate chain if your Skype for Business deployment is using a public certificate (for example, Entrust, VeriSign, and so on).</span></span> 
    
<span data-ttu-id="c64db-126">Se você planeja ingressar máquinas do Sistema de Sala do Skype no domínio, para evitar ingressar inadvertidamente na máquina do Sistema de Sala do Skype em uma UO não intencional, que pode não estar livre de GPOs, certifique-se de ingressar na UO correta.</span><span class="sxs-lookup"><span data-stu-id="c64db-126">If you plan to join Skype Room System machines to the domain, to avoid joining Skype Room System machine inadvertently to an unintended OU, which may not be free from GPOs, please ensure you join the correct OU.</span></span> <span data-ttu-id="c64db-127">Você pode usar o seguinte cmdlet da máquina do Sistema de Sala do Skype para ingressar na UO correta e não recebe GPOs que podem bloquear a funcionalidade do LRS.</span><span class="sxs-lookup"><span data-stu-id="c64db-127">You can use the following cmdlet from the Skype Room System machine to join in the correct OU and does not receive GPOs that might block LRS functionality.</span></span> <span data-ttu-id="c64db-128">Entre em contato com o administrador do sistema ou com o parceiro OEM para executar estes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="c64db-128">Contact your system administrator or OEM partner to run these cmdlet:</span></span>
  
```powershell
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

<span data-ttu-id="c64db-129">Mesmo que você crie uma UO separada e bloqueie a herança, há algumas políticas que podem causar problemas em um nível superior.</span><span class="sxs-lookup"><span data-stu-id="c64db-129">Even if you create a separate OU and block inheritance, there are some policies which could cause issues at a higher level.</span></span> <span data-ttu-id="c64db-130">Uma configuração política de grupo sem substituição supera uma UO com uma configuração bloquear herança de política.</span><span class="sxs-lookup"><span data-stu-id="c64db-130">A Group Policy with No Override setting beats an OU with a Block Policy Inheritance setting.</span></span> <span data-ttu-id="c64db-131">Para obter mais informações, consulte o artigo [No Override as Compared to Block Policy Inheritance](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) na documentação da Política de Grupo.</span><span class="sxs-lookup"><span data-stu-id="c64db-131">For more information, see the article [No Override as Compared to Block Policy Inheritance](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) in the Group Policy documentation.</span></span>
  
<span data-ttu-id="c64db-132">Você pode ter várias abordagens para resolver esses problemas.</span><span class="sxs-lookup"><span data-stu-id="c64db-132">You may have multiple approaches to solving these problems.</span></span> <span data-ttu-id="c64db-133">Aconselhamos você a consultar seus especialistas do Active Directory para garantir que você tenha uma UO que tenha as configurações de GPO apropriadas ou pelo menos uma UO na qual as políticas descritas anteriormente não existam.</span><span class="sxs-lookup"><span data-stu-id="c64db-133">We advise you to consult with your Active Directory experts to ensure you are provided with an OU that has appropriate GPO settings, or at least an OU in which the previously described policies do not exist.</span></span> <span data-ttu-id="c64db-134">É aconselhável habilitar a QoS (Qualidade de Serviço) para dispositivos do Sistema de Sala do Skype.</span><span class="sxs-lookup"><span data-stu-id="c64db-134">It is advised to enable Quality of Service (QoS) for Skype Room System devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="c64db-135">Confira também</span><span class="sxs-lookup"><span data-stu-id="c64db-135">See also</span></span>
  
[<span data-ttu-id="c64db-136">Configuração de Dispositivo: Criar Nova ou Editar Existente</span><span class="sxs-lookup"><span data-stu-id="c64db-136">Device Configuration: Create New or Edit Existing</span></span>](../../help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[<span data-ttu-id="c64db-137">Gerenciando a Qualidade de Serviço</span><span class="sxs-lookup"><span data-stu-id="c64db-137">Managing Quality of Service</span></span>](../../plan-your-deployment/network-requirements/network-requirements.md#managing-quality-of-service)
