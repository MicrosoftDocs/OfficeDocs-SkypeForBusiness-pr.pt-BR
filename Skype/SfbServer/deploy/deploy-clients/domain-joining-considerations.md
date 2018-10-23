---
title: Considerações de ingresso no domínio do Sistema de Salas do Skype
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3034fdcb-7c89-42c4-9c5e-13400e82d88f
description: Leia este tópico para saber como ingressar o PC do cliente do Sistema de Salas do Skype em seu domínio.
ms.openlocfilehash: 3a457e73b3509967043b1ef11d1e5017f2190434
ms.sourcegitcommit: d3c3467320a2928d3bad14a1a44a31ee5a9a988c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/23/2018
ms.locfileid: "25699592"
---
# <a name="skype-room-system-domain-joining-considerations"></a><span data-ttu-id="b3616-103">Considerações de ingresso no domínio do Sistema de Salas do Skype</span><span class="sxs-lookup"><span data-stu-id="b3616-103">Skype Room System domain joining considerations</span></span>
 
<span data-ttu-id="b3616-104">Leia este tópico para saber como ingressar o PC do cliente do Sistema de Salas do Skype em seu domínio.</span><span class="sxs-lookup"><span data-stu-id="b3616-104">Read this topic to learn how to join a Skype Room System appliance PC to your domain.</span></span>
  
## <a name="domain-joining-considerations"></a><span data-ttu-id="b3616-105">Considerações de ingresso no Domínio</span><span class="sxs-lookup"><span data-stu-id="b3616-105">Domain joining considerations</span></span>

<span data-ttu-id="b3616-106">Você pode ingressar o aparelho de sistema de sala Skype PC no domínio do Active Directory ou deixá-lo em um grupo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="b3616-106">You can join the Skype Room System appliance PC to the Active Directory domain or leave it in a Workgroup.</span></span> <span data-ttu-id="b3616-107">Considere os seguintes pontos antes da tomada desta decisão:</span><span class="sxs-lookup"><span data-stu-id="b3616-107">Consider the following points before making this decision:</span></span>
  
- <span data-ttu-id="b3616-108">O aparelho de sistema de sala Skype PC ingressando em domínio ajuda na importação de cadeia de certificados raiz privados da sua organização automaticamente.</span><span class="sxs-lookup"><span data-stu-id="b3616-108">Domain-joining the Skype Room System appliance PC helps in importing your organization's private root certificate chain automatically.</span></span>
    
- <span data-ttu-id="b3616-109">O aparelho de sistema de sala Skype PC ingressando em domínio permite conceder direitos administrativos de grupos e de usuários do domínio.</span><span class="sxs-lookup"><span data-stu-id="b3616-109">Domain-joining the Skype Room System appliance PC enables you to grant domain users and groups administrative rights.</span></span> <span data-ttu-id="b3616-110">Ao fazer isso, você não precisará ter que se lembrar da senha da conta do administrador no nível da máquina local.</span><span class="sxs-lookup"><span data-stu-id="b3616-110">By doing so, you will not have to remember the local machine level administrator account password.</span></span>
    
- <span data-ttu-id="b3616-111">Quando você associa um aparelho de sistema de sala Skype PC ao domínio, é necessário que você crie um separado OU (unidade organizacional), para que você possa fornecer exclusões de objeto de diretiva de grupo (GPO) para a UO na qual todos os objetos de máquina de sistema de sala Skype residem.</span><span class="sxs-lookup"><span data-stu-id="b3616-111">When you join an Skype Room System appliance PC to the domain, it is required that you create a separate Organizational Unit (OU), so that you can provide Group Policy Object (GPO) exclusions to the OU where all the Skype Room System machine objects reside.</span></span> <span data-ttu-id="b3616-112">Quando você fizer isso, crie objetos de computador na unidade Organizacional antes de ingressar o aparelho de sistema de sala Skype PC no domínio.</span><span class="sxs-lookup"><span data-stu-id="b3616-112">When you do this, create machine objects in the OU before joining the Skype Room System appliance PC to the domain.</span></span>
    
- <span data-ttu-id="b3616-113">Muitas organizações têm os GPOs a seguir, que afetam as funções do sistema de sala Skype appliance PC.</span><span class="sxs-lookup"><span data-stu-id="b3616-113">Many organizations have the following GPOs, which affect Skype Room System appliance PC functions.</span></span> <span data-ttu-id="b3616-114">Certifique-se de que você deseja substituir ou bloquear a herança desses GPOs na UO Skype sala sistema:</span><span class="sxs-lookup"><span data-stu-id="b3616-114">Ensure that you override or block the inheritance of these GPOs in the Skype Room System OU:</span></span> 
    
  - <span data-ttu-id="b3616-115">Tempo limite de sessões de logon (bloqueio automático)</span><span class="sxs-lookup"><span data-stu-id="b3616-115">Timeout of logon sessions (auto lockout)</span></span>
    
  - <span data-ttu-id="b3616-116">Políticas relacionadas ao gerenciamento de energia</span><span class="sxs-lookup"><span data-stu-id="b3616-116">Power management related policies</span></span>
    
  - <span data-ttu-id="b3616-117">Requerendo etapas adicionais de autenticação</span><span class="sxs-lookup"><span data-stu-id="b3616-117">Requiring additional authentication steps</span></span>
    
  - <span data-ttu-id="b3616-118">Negando acesso a unidades locais</span><span class="sxs-lookup"><span data-stu-id="b3616-118">Denying access to local drives</span></span>
    
  - <span data-ttu-id="b3616-119">Avisando usuários para conexões de rede lentas</span><span class="sxs-lookup"><span data-stu-id="b3616-119">Prompting users for slow network connections</span></span>
    
  - <span data-ttu-id="b3616-120">Iniciar um determinado programa no logon</span><span class="sxs-lookup"><span data-stu-id="b3616-120">Start a certain program at logon</span></span>
    
  - <span data-ttu-id="b3616-121">Crie uma outra conta de usuário de domínio em todas as máquinas que ingressaram no domínio.</span><span class="sxs-lookup"><span data-stu-id="b3616-121">Create another domain user account on all domain-joined machines.</span></span>
    
  - <span data-ttu-id="b3616-122">Enviar o Windows Update para o sistema de sala do Skype</span><span class="sxs-lookup"><span data-stu-id="b3616-122">Push Windows Update to Skype Room System</span></span>
    
- <span data-ttu-id="b3616-123">Opcionalmente, você pode optar por deixar o PC de cliente no grupo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="b3616-123">Alternatively, you might decide to leave the appliance PC in the workgroup.</span></span> <span data-ttu-id="b3616-124">Como com a área de trabalho Skype para o cliente de negócios, isso requer que você importar manualmente a cadeia de certificados raiz no dispositivo do sistema de sala Skype PC.</span><span class="sxs-lookup"><span data-stu-id="b3616-124">As with the desktop Skype for Business client, this requires you to manually import the root certificate chain on the Skype Room System appliance PC.</span></span> <span data-ttu-id="b3616-125">Você não precisa importar a cadeia de certificados raiz, se sua Skype para implantação de negócios está usando um certificado público (por exemplo, Entrust, VeriSign e assim por diante).</span><span class="sxs-lookup"><span data-stu-id="b3616-125">You're not required to import the root certificate chain if your Skype for Business deployment is using a public certificate (for example, Entrust, VeriSign, and so on).</span></span> 
    
<span data-ttu-id="b3616-126">Se você planeja ingresse máquinas Skype sala sistema no domínio, para evitar a ingressar na máquina do sistema de sala Skype inadvertidamente para uma UO acidentais, que pode não estar livre de GPOs, verifique se que você ingressar a UO correta.</span><span class="sxs-lookup"><span data-stu-id="b3616-126">If you plan to join Skype Room System machines to the domain, to avoid joining Skype Room System machine inadvertently to an unintended OU, which may not be free from GPOs, please ensure you join the correct OU.</span></span> <span data-ttu-id="b3616-127">Você pode usar o seguinte cmdlet da máquina Skype sistema de sala para ingressar na unidade Organizacional correto e não recebe GPOs que podem bloquear a funcionalidade LRS.</span><span class="sxs-lookup"><span data-stu-id="b3616-127">You can use the following cmdlet from the Skype Room System machine to join in the correct OU and does not receive GPOs that might block LRS functionality.</span></span> <span data-ttu-id="b3616-128">Entre em contato com o administrador do sistema ou com o parceiro OEM para executar esses cmdlet:</span><span class="sxs-lookup"><span data-stu-id="b3616-128">Contact your system administrator or OEM partner to run these cmdlet:</span></span>
  
```
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

<span data-ttu-id="b3616-129">Mesmo que você crie uma Unidade Organizacional e bloqueie herança, há algumas políticas que podem causar problemas a um nível superior.</span><span class="sxs-lookup"><span data-stu-id="b3616-129">Even if you create a separate OU and block inheritance, there are some policies which could cause issues at a higher level.</span></span> <span data-ttu-id="b3616-130">A configuração Política de Grupo sem Substituição supera uma UO com uma configuração Bloquear Herança de Política.</span><span class="sxs-lookup"><span data-stu-id="b3616-130">A Group Policy with No Override setting beats an OU with a Block Policy Inheritance setting.</span></span> <span data-ttu-id="b3616-131">Para obter mais informações, consulte o artigo [Não substituir em relação ao bloquear herança de diretiva](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) na documentação de diretiva de grupo.</span><span class="sxs-lookup"><span data-stu-id="b3616-131">For more information, see the article [No Override as Compared to Block Policy Inheritance](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) in the Group Policy documentation.</span></span>
  
<span data-ttu-id="b3616-132">Você pode ter várias abordagens para resolver esses problemas.</span><span class="sxs-lookup"><span data-stu-id="b3616-132">You may have multiple approaches to solving these problems.</span></span> <span data-ttu-id="b3616-133">Recomendamos que você consulte os especialistas em Active Directory para garantir que sejam fornecidas a você as configurações de GPO apropriadas ou pelo menos uma Unidade Organizacional na qual as políticas descritas anteriormente não existem.</span><span class="sxs-lookup"><span data-stu-id="b3616-133">We advise you to consult with your Active Directory experts to ensure you are provided with an OU that has appropriate GPO settings, or at least an OU in which the previously described policies do not exist.</span></span> <span data-ttu-id="b3616-134">É recomendável para habilitar o Quality of Service (QoS) para dispositivos de sistema do Skype sala.</span><span class="sxs-lookup"><span data-stu-id="b3616-134">It is advised to enable Quality of Service (QoS) for Skype Room System devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="b3616-135">Consulte também</span><span class="sxs-lookup"><span data-stu-id="b3616-135">See also</span></span>
  
[<span data-ttu-id="b3616-136">Configuração de Dispositivo: Criar Nova ou Editar Existente</span><span class="sxs-lookup"><span data-stu-id="b3616-136">Device Configuration: Create New or Edit Existing</span></span>](../../help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[<span data-ttu-id="b3616-137">Gerenciando a Qualidade de Serviço</span><span class="sxs-lookup"><span data-stu-id="b3616-137">Managing Quality of Service</span></span>](../../plan-your-deployment/network-requirements/network-requirements.md#managing-quality-of-service)
