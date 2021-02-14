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
description: O administrador pode saber mais sobre como ingressar em um pc de dispositivo do Skype Room System em um domínio do Active Directory, juntamente com as considerações para fazê-lo.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: dfcee1421c25903a5ec8deb2f66871ed1d57ef1c
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905433"
---
<!-- This asset missed in the rebrand, and honestly not sure if it's worth keeping.   -->

# <a name="skype-room-system-domain-joining-considerations"></a><span data-ttu-id="8f4a8-103">Considerações de ingresso no domínio do Sistema de Salas do Skype</span><span class="sxs-lookup"><span data-stu-id="8f4a8-103">Skype Room System domain joining considerations</span></span>
 
<span data-ttu-id="8f4a8-104">Leia este tópico para saber como ingressar o PC do cliente do Sistema de Salas do Skype em seu domínio.</span><span class="sxs-lookup"><span data-stu-id="8f4a8-104">Read this topic to learn how to join a Skype Room System appliance PC to your domain.</span></span>
  
## <a name="domain-joining-considerations"></a><span data-ttu-id="8f4a8-105">Considerações de ingresso no Domínio</span><span class="sxs-lookup"><span data-stu-id="8f4a8-105">Domain joining considerations</span></span>

<span data-ttu-id="8f4a8-106">Você pode ingressar no computador do dispositivo Skype Room System para o domínio do Active Directory ou deixá-lo em um Grupo de Trabalho.</span><span class="sxs-lookup"><span data-stu-id="8f4a8-106">You can join the Skype Room System appliance PC to the Active Directory domain or leave it in a Workgroup.</span></span> <span data-ttu-id="8f4a8-107">Considere os seguintes pontos antes da tomada desta decisão:</span><span class="sxs-lookup"><span data-stu-id="8f4a8-107">Consider the following points before making this decision:</span></span>
  
- <span data-ttu-id="8f4a8-108">A junção de domínios no computador do dispositivo Skype Room System ajuda a importar automaticamente a cadeia de certificado raiz privada da sua organização.</span><span class="sxs-lookup"><span data-stu-id="8f4a8-108">Domain-joining the Skype Room System appliance PC helps in importing your organization's private root certificate chain automatically.</span></span>
- <span data-ttu-id="8f4a8-109">A junção de domínios no computador do dispositivo Skype Room System permite que você conceda direitos administrativos a usuários de domínios e grupos.</span><span class="sxs-lookup"><span data-stu-id="8f4a8-109">Domain-joining the Skype Room System appliance PC enables you to grant domain users and groups administrative rights.</span></span> <span data-ttu-id="8f4a8-110">Ao fazer isso, você não precisará ter que se lembrar da senha da conta do administrador no nível da máquina local.</span><span class="sxs-lookup"><span data-stu-id="8f4a8-110">By doing so, you will not have to remember the local machine level administrator account password.</span></span>
- <span data-ttu-id="8f4a8-111">Ao ingressar em um computador móvel do Sistema de Salas do Skype com o domínio, é necessário criar uma Unidade Organizacional (OU) separada, para que você possa fornecer exclusões de OBJETO de Política de Grupo (GPO) para a UO onde residem todos os objetos de máquina do Sistema de Salas do Skype.</span><span class="sxs-lookup"><span data-stu-id="8f4a8-111">When you join an Skype Room System appliance PC to the domain, it is required that you create a separate Organizational Unit (OU), so that you can provide Group Policy Object (GPO) exclusions to the OU where all the Skype Room System machine objects reside.</span></span> <span data-ttu-id="8f4a8-112">Quando você fizer isso, crie objetos de máquina na UO antes de ingressar no computador de dispositivo do Sistema de Sala do Skype ao domínio.</span><span class="sxs-lookup"><span data-stu-id="8f4a8-112">When you do this, create machine objects in the OU before joining the Skype Room System appliance PC to the domain.</span></span>
- <span data-ttu-id="8f4a8-113">Muitas organizações têm os seguintes GPOs, que afetam as funções do computador do dispositivo Skype Room System.</span><span class="sxs-lookup"><span data-stu-id="8f4a8-113">Many organizations have the following GPOs, which affect Skype Room System appliance PC functions.</span></span> <span data-ttu-id="8f4a8-114">Verifique se você substitui ou bloqueia a herança desses GPOs no Skype Room System OU:</span><span class="sxs-lookup"><span data-stu-id="8f4a8-114">Ensure that you override or block the inheritance of these GPOs in the Skype Room System OU:</span></span>

  - <span data-ttu-id="8f4a8-115">Tempo limite de sessões de logon (bloqueio automático)</span><span class="sxs-lookup"><span data-stu-id="8f4a8-115">Timeout of logon sessions (auto lockout)</span></span>
  - <span data-ttu-id="8f4a8-116">Políticas relacionadas ao gerenciamento de energia</span><span class="sxs-lookup"><span data-stu-id="8f4a8-116">Power management related policies</span></span>
  - <span data-ttu-id="8f4a8-117">Requerendo etapas adicionais de autenticação</span><span class="sxs-lookup"><span data-stu-id="8f4a8-117">Requiring additional authentication steps</span></span>
  - <span data-ttu-id="8f4a8-118">Negando acesso a unidades locais</span><span class="sxs-lookup"><span data-stu-id="8f4a8-118">Denying access to local drives</span></span>
  - <span data-ttu-id="8f4a8-119">Avisando usuários para conexões de rede lentas</span><span class="sxs-lookup"><span data-stu-id="8f4a8-119">Prompting users for slow network connections</span></span>
  - <span data-ttu-id="8f4a8-120">Iniciar um determinado programa no logon</span><span class="sxs-lookup"><span data-stu-id="8f4a8-120">Start a certain program at logon</span></span>
  - <span data-ttu-id="8f4a8-121">Crie uma outra conta de usuário de domínio em todas as máquinas que ingressaram no domínio.</span><span class="sxs-lookup"><span data-stu-id="8f4a8-121">Create another domain user account on all domain-joined machines.</span></span>
  - <span data-ttu-id="8f4a8-122">Push Windows Update to Skype Room System</span><span class="sxs-lookup"><span data-stu-id="8f4a8-122">Push Windows Update to Skype Room System</span></span>
    
- <span data-ttu-id="8f4a8-123">Opcionalmente, você pode optar por deixar o PC de cliente no grupo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="8f4a8-123">Alternatively, you might decide to leave the appliance PC in the workgroup.</span></span> <span data-ttu-id="8f4a8-124">Assim como no cliente da área de trabalho do Microsoft Teams ou do Skype for Business, isso exige que você importe manualmente a cadeia de certificado raiz no computador do dispositivo Skype Room System.</span><span class="sxs-lookup"><span data-stu-id="8f4a8-124">As with the desktop Microsoft Teams or Skype for Business client, this requires you to manually import the root certificate chain on the Skype Room System appliance PC.</span></span> <span data-ttu-id="8f4a8-125">Você não será obrigado a importar a cadeia de certificados raiz se sua implantação estiver usando um certificado público (por exemplo, Confie, VeriSign e assim por diante).</span><span class="sxs-lookup"><span data-stu-id="8f4a8-125">You're not required to import the root certificate chain if your deployment is using a public certificate (for example, Entrust, VeriSign, and so on).</span></span> 
    
<span data-ttu-id="8f4a8-126">Se você planeja ingressar em máquinas do Sistema de Sala do Skype para o domínio, para evitar ingressar inadvertidamente em uma OU não intencional, que pode não ser gratuita de GPOs, certifique-se de ingressar na O ou correta.</span><span class="sxs-lookup"><span data-stu-id="8f4a8-126">If you plan to join Skype Room System machines to the domain, to avoid joining Skype Room System machine inadvertently to an unintended OU, which may not be free from GPOs, please ensure you join the correct OU.</span></span> <span data-ttu-id="8f4a8-127">Você pode usar o seguinte cmdlet do computador Skype Room System para ingressar na OU correta e não recebe GPOs que podem bloquear a funcionalidade LRS.</span><span class="sxs-lookup"><span data-stu-id="8f4a8-127">You can use the following cmdlet from the Skype Room System machine to join in the correct OU and does not receive GPOs that might block LRS functionality.</span></span> <span data-ttu-id="8f4a8-128">Entre em contato com o administrador do sistema ou com o parceiro OEM para executar esses cmdlet:</span><span class="sxs-lookup"><span data-stu-id="8f4a8-128">Contact your system administrator or OEM partner to run these cmdlet:</span></span>
  
```
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

<span data-ttu-id="8f4a8-129">Mesmo que você crie uma Unidade Organizacional e bloqueie herança, há algumas políticas que podem causar problemas a um nível superior.</span><span class="sxs-lookup"><span data-stu-id="8f4a8-129">Even if you create a separate OU and block inheritance, there are some policies which could cause issues at a higher level.</span></span> <span data-ttu-id="8f4a8-130">A configuração Política de Grupo sem Substituição supera uma UO com uma configuração Bloquear Herança de Política.</span><span class="sxs-lookup"><span data-stu-id="8f4a8-130">A Group Policy with No Override setting beats an OU with a Block Policy Inheritance setting.</span></span> <span data-ttu-id="8f4a8-131">Para obter mais informações, consulte o artigo Sem Substituição em Comparação com a Herança [de Política de](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) Bloqueio na documentação da Política de Grupo.</span><span class="sxs-lookup"><span data-stu-id="8f4a8-131">For more information, see the article [No Override as Compared to Block Policy Inheritance](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) in the Group Policy documentation.</span></span>
  
<span data-ttu-id="8f4a8-132">Você pode ter várias abordagens para resolver esses problemas.</span><span class="sxs-lookup"><span data-stu-id="8f4a8-132">You may have multiple approaches to solving these problems.</span></span> <span data-ttu-id="8f4a8-133">Recomendamos que você consulte os especialistas em Active Directory para garantir que sejam fornecidas a você as configurações de GPO apropriadas ou pelo menos uma Unidade Organizacional na qual as políticas descritas anteriormente não existem.</span><span class="sxs-lookup"><span data-stu-id="8f4a8-133">We advise you to consult with your Active Directory experts to ensure you are provided with an OU that has appropriate GPO settings, or at least an OU in which the previously described policies do not exist.</span></span> <span data-ttu-id="8f4a8-134">É aconselhável habilitar a QoS (Qualidade de Serviço) para dispositivos do Skype Room System.</span><span class="sxs-lookup"><span data-stu-id="8f4a8-134">It is advised to enable Quality of Service (QoS) for Skype Room System devices.</span></span>

## <a name="related-topics"></a><span data-ttu-id="8f4a8-135">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="8f4a8-135">Related topics</span></span>
  
[<span data-ttu-id="8f4a8-136">Configuração de Dispositivo: Criar Nova ou Editar Existente</span><span class="sxs-lookup"><span data-stu-id="8f4a8-136">Device Configuration: Create New or Edit Existing</span></span>](/skypeforbusiness/help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[<span data-ttu-id="8f4a8-137">Gerenciando a Qualidade de Serviço</span><span class="sxs-lookup"><span data-stu-id="8f4a8-137">Managing Quality of Service</span></span>](/skypeforbusiness/plan-your-deployment/network-requirements/network-requirements.#managing-quality-of-service)
