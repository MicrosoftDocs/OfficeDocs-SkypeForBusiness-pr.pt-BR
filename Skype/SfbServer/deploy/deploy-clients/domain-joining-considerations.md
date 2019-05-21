---
title: Considerações de ingresso no domínio do Sistema de Salas do Skype
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3034fdcb-7c89-42c4-9c5e-13400e82d88f
description: Leia este tópico para saber como ingressar o PC do cliente do Sistema de Salas do Skype em seu domínio.
ms.openlocfilehash: 934b39a0375085e9b8c18022a4526c76a970aca9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34293610"
---
# <a name="skype-room-system-domain-joining-considerations"></a><span data-ttu-id="ae492-103">Considerações de ingresso no domínio do Sistema de Salas do Skype</span><span class="sxs-lookup"><span data-stu-id="ae492-103">Skype Room System domain joining considerations</span></span>
 
<span data-ttu-id="ae492-104">Leia este tópico para saber como ingressar o PC do cliente do Sistema de Salas do Skype em seu domínio.</span><span class="sxs-lookup"><span data-stu-id="ae492-104">Read this topic to learn how to join a Skype Room System appliance PC to your domain.</span></span>
  
## <a name="domain-joining-considerations"></a><span data-ttu-id="ae492-105">Considerações de ingresso no Domínio</span><span class="sxs-lookup"><span data-stu-id="ae492-105">Domain joining considerations</span></span>

<span data-ttu-id="ae492-106">Você pode participar do PC de utensílios do sistema da sala Skype ao domínio do Active Directory ou deixá-lo em um grupo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="ae492-106">You can join the Skype Room System appliance PC to the Active Directory domain or leave it in a Workgroup.</span></span> <span data-ttu-id="ae492-107">Considere os seguintes pontos antes da tomada desta decisão:</span><span class="sxs-lookup"><span data-stu-id="ae492-107">Consider the following points before making this decision:</span></span>
  
- <span data-ttu-id="ae492-108">Domínio-participar do PC Appliance do sistema de sala do Skype ajuda a importar a cadeia de certificados raiz particulares da sua organização automaticamente.</span><span class="sxs-lookup"><span data-stu-id="ae492-108">Domain-joining the Skype Room System appliance PC helps in importing your organization's private root certificate chain automatically.</span></span>
    
- <span data-ttu-id="ae492-109">Domínio-participar do PC Appliance da sala do Skype permite que você conceda direitos administrativos a usuários e grupos de domínio.</span><span class="sxs-lookup"><span data-stu-id="ae492-109">Domain-joining the Skype Room System appliance PC enables you to grant domain users and groups administrative rights.</span></span> <span data-ttu-id="ae492-110">Ao fazer isso, você não precisará ter que se lembrar da senha da conta do administrador no nível da máquina local.</span><span class="sxs-lookup"><span data-stu-id="ae492-110">By doing so, you will not have to remember the local machine level administrator account password.</span></span>
    
- <span data-ttu-id="ae492-111">Quando você ingressa em um computador com um aparelho de sistema de sala do Skype para o domínio, é necessário criar uma unidade organizacional (OU) separada para que você possa fornecer exclusões do objeto de política de grupo (GPO) à OU em que todos os objetos do computador do sistema de sala do Skype residem.</span><span class="sxs-lookup"><span data-stu-id="ae492-111">When you join an Skype Room System appliance PC to the domain, it is required that you create a separate Organizational Unit (OU), so that you can provide Group Policy Object (GPO) exclusions to the OU where all the Skype Room System machine objects reside.</span></span> <span data-ttu-id="ae492-112">Ao fazer isso, crie objetos de máquina na UO antes de ingressar no computador do aparelho de sistema de sala do Skype para o domínio.</span><span class="sxs-lookup"><span data-stu-id="ae492-112">When you do this, create machine objects in the OU before joining the Skype Room System appliance PC to the domain.</span></span>
    
- <span data-ttu-id="ae492-113">Muitas organizações têm os seguintes GPOs, que afetam as funções do PC Appliance do Skype Room System.</span><span class="sxs-lookup"><span data-stu-id="ae492-113">Many organizations have the following GPOs, which affect Skype Room System appliance PC functions.</span></span> <span data-ttu-id="ae492-114">Certifique-se de substituir ou bloquear a herança dos GPOs na unidade organizacional do sistema de sala do Skype:</span><span class="sxs-lookup"><span data-stu-id="ae492-114">Ensure that you override or block the inheritance of these GPOs in the Skype Room System OU:</span></span> 
    
  - <span data-ttu-id="ae492-115">Tempo limite de sessões de logon (bloqueio automático)</span><span class="sxs-lookup"><span data-stu-id="ae492-115">Timeout of logon sessions (auto lockout)</span></span>
    
  - <span data-ttu-id="ae492-116">Políticas relacionadas ao gerenciamento de energia</span><span class="sxs-lookup"><span data-stu-id="ae492-116">Power management related policies</span></span>
    
  - <span data-ttu-id="ae492-117">Requerendo etapas adicionais de autenticação</span><span class="sxs-lookup"><span data-stu-id="ae492-117">Requiring additional authentication steps</span></span>
    
  - <span data-ttu-id="ae492-118">Negando acesso a unidades locais</span><span class="sxs-lookup"><span data-stu-id="ae492-118">Denying access to local drives</span></span>
    
  - <span data-ttu-id="ae492-119">Avisando usuários para conexões de rede lentas</span><span class="sxs-lookup"><span data-stu-id="ae492-119">Prompting users for slow network connections</span></span>
    
  - <span data-ttu-id="ae492-120">Iniciar um determinado programa no logon</span><span class="sxs-lookup"><span data-stu-id="ae492-120">Start a certain program at logon</span></span>
    
  - <span data-ttu-id="ae492-121">Crie uma outra conta de usuário de domínio em todas as máquinas que ingressaram no domínio.</span><span class="sxs-lookup"><span data-stu-id="ae492-121">Create another domain user account on all domain-joined machines.</span></span>
    
  - <span data-ttu-id="ae492-122">Envie o Windows Update para o sistema de sala da Skype</span><span class="sxs-lookup"><span data-stu-id="ae492-122">Push Windows Update to Skype Room System</span></span>
    
- <span data-ttu-id="ae492-123">Opcionalmente, você pode optar por deixar o PC de cliente no grupo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="ae492-123">Alternatively, you might decide to leave the appliance PC in the workgroup.</span></span> <span data-ttu-id="ae492-124">Assim como no cliente do Skype for Business da área de trabalho, isso exige que você importe manualmente a cadeia de certificados raiz no PC da ferramenta de sistema da sala do Skype.</span><span class="sxs-lookup"><span data-stu-id="ae492-124">As with the desktop Skype for Business client, this requires you to manually import the root certificate chain on the Skype Room System appliance PC.</span></span> <span data-ttu-id="ae492-125">Você não será obrigado a importar a cadeia de certificados raiz se a implantação do Skype for Business estiver usando um certificado público (por exemplo, Entrust, VeriSign e assim por diante).</span><span class="sxs-lookup"><span data-stu-id="ae492-125">You're not required to import the root certificate chain if your Skype for Business deployment is using a public certificate (for example, Entrust, VeriSign, and so on).</span></span> 
    
<span data-ttu-id="ae492-126">Se você planeja ingressar em máquinas do sistema de sala do Skype no domínio, para evitar a União inadvertida da máquina do sistema de sala do Skype a uma UO não intencional, o que pode não ser gratuito dos GPOs, certifique-se de participar da UO correta.</span><span class="sxs-lookup"><span data-stu-id="ae492-126">If you plan to join Skype Room System machines to the domain, to avoid joining Skype Room System machine inadvertently to an unintended OU, which may not be free from GPOs, please ensure you join the correct OU.</span></span> <span data-ttu-id="ae492-127">Você pode usar o cmdlet a seguir da máquina do sistema de sala do Skype para ingressar na UO correta e não receber GPOs que possam bloquear a funcionalidade LRS.</span><span class="sxs-lookup"><span data-stu-id="ae492-127">You can use the following cmdlet from the Skype Room System machine to join in the correct OU and does not receive GPOs that might block LRS functionality.</span></span> <span data-ttu-id="ae492-128">Entre em contato com o administrador do sistema ou com o parceiro OEM para executar esses cmdlet:</span><span class="sxs-lookup"><span data-stu-id="ae492-128">Contact your system administrator or OEM partner to run these cmdlet:</span></span>
  
```
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

<span data-ttu-id="ae492-129">Mesmo que você crie uma Unidade Organizacional e bloqueie herança, há algumas políticas que podem causar problemas a um nível superior.</span><span class="sxs-lookup"><span data-stu-id="ae492-129">Even if you create a separate OU and block inheritance, there are some policies which could cause issues at a higher level.</span></span> <span data-ttu-id="ae492-130">A configuração Política de Grupo sem Substituição supera uma UO com uma configuração Bloquear Herança de Política.</span><span class="sxs-lookup"><span data-stu-id="ae492-130">A Group Policy with No Override setting beats an OU with a Block Policy Inheritance setting.</span></span> <span data-ttu-id="ae492-131">Para obter mais informações, consulte o artigo [não substituir quando comparado à herança da política de bloqueio](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) na documentação da política de grupo.</span><span class="sxs-lookup"><span data-stu-id="ae492-131">For more information, see the article [No Override as Compared to Block Policy Inheritance](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) in the Group Policy documentation.</span></span>
  
<span data-ttu-id="ae492-132">Você pode ter várias abordagens para resolver esses problemas.</span><span class="sxs-lookup"><span data-stu-id="ae492-132">You may have multiple approaches to solving these problems.</span></span> <span data-ttu-id="ae492-133">Recomendamos que você consulte os especialistas em Active Directory para garantir que sejam fornecidas a você as configurações de GPO apropriadas ou pelo menos uma Unidade Organizacional na qual as políticas descritas anteriormente não existem.</span><span class="sxs-lookup"><span data-stu-id="ae492-133">We advise you to consult with your Active Directory experts to ensure you are provided with an OU that has appropriate GPO settings, or at least an OU in which the previously described policies do not exist.</span></span> <span data-ttu-id="ae492-134">É recomendável habilitar a QoS (qualidade de serviço) para dispositivos do sistema de sala do Skype.</span><span class="sxs-lookup"><span data-stu-id="ae492-134">It is advised to enable Quality of Service (QoS) for Skype Room System devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="ae492-135">Confira também</span><span class="sxs-lookup"><span data-stu-id="ae492-135">See also</span></span>
  
[<span data-ttu-id="ae492-136">Configuração de Dispositivo: Criar Nova ou Editar Existente</span><span class="sxs-lookup"><span data-stu-id="ae492-136">Device Configuration: Create New or Edit Existing</span></span>](../../help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[<span data-ttu-id="ae492-137">Gerenciando a Qualidade de Serviço</span><span class="sxs-lookup"><span data-stu-id="ae492-137">Managing Quality of Service</span></span>](../../plan-your-deployment/network-requirements/network-requirements.md#managing-quality-of-service)
