---
title: Guia de Segurança do Microsoft Teams
author: MSFTTracyP
ms.author: tracyp
manager: dansimp
ms.date: 08/21/2020
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: pawa
description: Orientações para usar o Microsoft Teams de forma segura em um computador compartilhado no local de trabalho.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: a723a7300febde4eaa5045b9b1318a3e0cafe779
ms.sourcegitcommit: cd16ff6007e0a798493e2fa469c6681993380420
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/23/2020
ms.locfileid: "46860822"
---
# <a name="use-microsoft-teams-securely-on-shared-computers"></a><span data-ttu-id="d4d9d-103">Usar o Microsoft Teams de forma segura em computadores compartilhados</span><span class="sxs-lookup"><span data-stu-id="d4d9d-103">Use Microsoft Teams securely on shared computers</span></span>

<span data-ttu-id="d4d9d-104">Sempre que possível, é *recomendável* que as empresas usem uma abordagem de Confiança Zero para dispositivos dos clientes que usam recursos de gerenciamento de dispositivos, verificações de integridade do dispositivo e imposição de política, criptografia no nível do dispositivo e outros recursos de segurança.</span><span class="sxs-lookup"><span data-stu-id="d4d9d-104">When possible, it is *recommended* Enterprises make use of a Zero Trust approach to client devices making use of device management capabilities, device health checks and policy enforcement, device-level encryption, and other security features.</span></span>

:::image type="content" source="media/tp_ZeroTrustPrinciples.PNG" alt-text="Imagem de Confiança Zero mostrando explicitamente a verificação, privilégios mínimos, e a suposição de violação (os principais princípios da Confiança Zero) nos círculos azuis.":::

<span data-ttu-id="d4d9d-106">Os administradores podem criar condições muito seguras, *insistindo* na verificação, no privilégio mínimo e supondo padrões de comprometimento que levem a ações que minimizem o risco para os usuários e dados.</span><span class="sxs-lookup"><span data-stu-id="d4d9d-106">Administrators can create very secure conditions by *insisting* on verification, least privilege, and by assuming compromise -- standards that lead to actions that minimize risk to both users and data.</span></span>

> [!TIP]
> <span data-ttu-id="d4d9d-107">Para uma análise mais profunda dos princípios de Confiança Zero, confira [esses vídeos](https://docs.microsoft.com/security/ciso-workshop/ciso-workshop-module-3#part-2-zero-trust-definition-and-models-1537).</span><span class="sxs-lookup"><span data-stu-id="d4d9d-107">For a deeper examination of Zero Trust principles, see [these videos](https://docs.microsoft.com/security/ciso-workshop/ciso-workshop-module-3#part-2-zero-trust-definition-and-models-1537).</span></span>

## <a name="tips-for-using-microsoft-teams-securely-from-a-shared-computer"></a><span data-ttu-id="d4d9d-108">Dicas para usar o Microsoft Teams de forma segura em um computador compartilhado</span><span class="sxs-lookup"><span data-stu-id="d4d9d-108">Tips for using Microsoft Teams securely from a shared computer</span></span>

<span data-ttu-id="d4d9d-109">Reconhecendo que isso possa não ser possível ou prático em todos os cenários, ainda é importante que os administradores de segurança entendam a orientação para usar o Teams de um computador compartilhado ou de um dispositivo não gerenciado da melhor forma possível.</span><span class="sxs-lookup"><span data-stu-id="d4d9d-109">Recognizing that this may not be possible or practical in all scenarios, it is still important for security administrators to follow guidance for using Teams from a shared computer or unmanaged device as best they can.</span></span>

<span data-ttu-id="d4d9d-110">Os planos devem ser desenvolvidos para seguir as orientações da maneira mais rápida possível.</span><span class="sxs-lookup"><span data-stu-id="d4d9d-110">Plans should be developed to adhere to guidelines as promptly as is possible.</span></span>

1. <span data-ttu-id="d4d9d-111">Usar os recursos de segurança da plataforma do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="d4d9d-111">Make use of Operating System platform security capabilities.</span></span>
    1. <span data-ttu-id="d4d9d-112">Verifique se o sistema operacional está configurado para instalar as atualizações automáticas do provedor do sistema operacional (para os sistemas da Microsoft, isso pode ser feito por meio do [**Windows Update**](https://support.microsoft.com/help/12373/windows-update-faq)).</span><span class="sxs-lookup"><span data-stu-id="d4d9d-112">Ensure that the operating system is configured to install automatic updates from the Operating System provider (for Microsoft systems, this can be accomplished via [**Windows Update**](https://support.microsoft.com/help/12373/windows-update-faq)).</span></span> 
    2. <span data-ttu-id="d4d9d-113">Certifique-se de que todos os recursos de criptografia, como [**BitLocker**](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) estão habilitados, e a chave usada para acessar o dispositivo está protegida.</span><span class="sxs-lookup"><span data-stu-id="d4d9d-113">Ensure that any device encryption capabilities such as [**bitlocker**](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) are enabled, and the key used to access the device is secured.</span></span>
    1. <span data-ttu-id="d4d9d-114">Use recursos antivírus, como os oferecidos pelo [**Windows Defender**](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) em seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="d4d9d-114">Use anti-virus capabilities such as those offered by [**Windows Defender**](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) on your devices.</span></span>
    1. <span data-ttu-id="d4d9d-115">É altamente recomendável usar o [contas de usuário separadas](https://support.microsoft.com/help/4026923/windows-10-create-a-local-user-or-administrator-account) para cada usuário do sistema.</span><span class="sxs-lookup"><span data-stu-id="d4d9d-115">Use of [separate user accounts](https://support.microsoft.com/help/4026923/windows-10-create-a-local-user-or-administrator-account) for each user of the system is highly recommended.</span></span>
    1. <span data-ttu-id="d4d9d-116">*Não* conceda nem use privilégios de administrador para funções não administrativas (como navegar na Web, executar o Teams, etc).</span><span class="sxs-lookup"><span data-stu-id="d4d9d-116">*Do not* grant, or use, administrator privileges for non-administrative functions (such as browsing the web, running Teams, et cetera).</span></span>

2. <span data-ttu-id="d4d9d-117">Aproveitar os recursos de segurança do navegador.</span><span class="sxs-lookup"><span data-stu-id="d4d9d-117">Leverage browser security capabilities.</span></span>
    1. <span data-ttu-id="d4d9d-118">Use sessões de navegação privadas para minimizar os dados e o histórico que continuam no disco.</span><span class="sxs-lookup"><span data-stu-id="d4d9d-118">Use private browsing sessions to minimize data and history that persists to disk.</span></span> <span data-ttu-id="d4d9d-119">Por exemplo, use a [navegação InPrivate no Microsoft Edge](https://support.microsoft.com/help/4533513/microsoft-edge-browse-inprivate), [a navegação incógnita no Google Chrome](https://support.google.com/chrome/answer/95464?co=GENIE.Platform%3DDesktop&hl=en)ou os recursos do seu navegador específico para navegar em privado.</span><span class="sxs-lookup"><span data-stu-id="d4d9d-119">For example, use [inPrivate browsing in Microsoft Edge](https://support.microsoft.com/help/4533513/microsoft-edge-browse-inprivate), [Incognito browsing in Google Chrome](https://support.google.com/chrome/answer/95464?co=GENIE.Platform%3DDesktop&hl=en), or the capabilities your specific browser for browsing privately.</span></span> 
    1. <span data-ttu-id="d4d9d-120">É recomendável alterar o comportamento do sistema para acionar a navegação privada *por padrão*.</span><span class="sxs-lookup"><span data-stu-id="d4d9d-120">Changing the system behavior to engage private browsing *by default* is recommended.</span></span> 

3. <span data-ttu-id="d4d9d-121">Navegue até e use o[aplicativo Web do Teams](https://teams.microsoft.com) (às vezes conhecido como cliente *web*) não o cliente para download do Teams.</span><span class="sxs-lookup"><span data-stu-id="d4d9d-121">Browse to and use the [Teams web app](https://teams.microsoft.com) (sometimes called the *web* client) not the downloadable Teams client.</span></span>

4. <span data-ttu-id="d4d9d-122">Quando terminar de usar o sistema compartilhado, você deve:</span><span class="sxs-lookup"><span data-stu-id="d4d9d-122">When you are done using the shared system, you must:</span></span> 
    1. <span data-ttu-id="d4d9d-123">[Sair do Microsoft Teams](https://support.microsoft.com/office/sign-out-of-teams-a6d76e69-e1dd-4bc4-8e5f-04ba48384487).</span><span class="sxs-lookup"><span data-stu-id="d4d9d-123">[Sign out of Teams](https://support.microsoft.com/office/sign-out-of-teams-a6d76e69-e1dd-4bc4-8e5f-04ba48384487).</span></span>
    1. <span data-ttu-id="d4d9d-124">Fechar todas as guias e janelas do navegador.</span><span class="sxs-lookup"><span data-stu-id="d4d9d-124">Close all browser tabs and windows.</span></span>
    1. <span data-ttu-id="d4d9d-125">Sair do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d4d9d-125">Sign out of the device.</span></span>

<span data-ttu-id="d4d9d-126">Os itens acima não são uma lista completa das práticas recomendadas ou dos controles de segurança que abrangem todos os casos, e podem haver ações adicionais que podem ser tomadas em seu ambiente (por exemplo, os administradores de segurança podem optar por usar links seguros e anexos seguros para o Teams, caso você tenha [o plano 1 ou 2 de Proteção Avançada contra Ameaças do Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide#office-365-atp-plan-1-and-plan-2)).</span><span class="sxs-lookup"><span data-stu-id="d4d9d-126">The items above are not a comprehensive list of best practices or security controls covering all cases, and there may be extra actions that can be taken in your environment, (for instance, security administrators may choose to use Safe Links and Safe Attachments for Teams if you have [Office 365 ATP Plan 1 or 2](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide#office-365-atp-plan-1-and-plan-2)).</span></span> <span data-ttu-id="d4d9d-127">No entanto, essas etapas são um ponto de partida para a criação de orientações para usar o Teams de dispositivos compartilhados.</span><span class="sxs-lookup"><span data-stu-id="d4d9d-127">However, these steps are a starting point for building guidance for using Teams from shared devices.</span></span>

## <a name="more-information"></a><span data-ttu-id="d4d9d-128">Mais informações</span><span class="sxs-lookup"><span data-stu-id="d4d9d-128">More Information</span></span>

[<span data-ttu-id="d4d9d-129">BitLocker no Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="d4d9d-129">Bitlocker in Configuration Manager</span></span>](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/bitlocker/deploy-management-agent)

[<span data-ttu-id="d4d9d-130">BitLocker para Windows 10 no Intune</span><span class="sxs-lookup"><span data-stu-id="d4d9d-130">Bitlocker for Windows 10 in Intune</span></span>](https://docs.microsoft.com/mem/intune/protect/encrypt-devices)

[<span data-ttu-id="d4d9d-131">Segurança do ponto de extremidade no Intune</span><span class="sxs-lookup"><span data-stu-id="d4d9d-131">Endpoint security in Intune</span></span>](https://docs.microsoft.com/mem/intune/protect/endpoint-security)

<span data-ttu-id="d4d9d-132">[Habilitar o](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus#ensure-microsoft-defender-antivirus-is-enabled-in-the-windows-security-app) Microsoft Defender Antivirus na Segurança do Windows e [executar exames](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus#run-a-scan-with-the-windows-security-app).</span><span class="sxs-lookup"><span data-stu-id="d4d9d-132">[Enable](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus#ensure-microsoft-defender-antivirus-is-enabled-in-the-windows-security-app) Microsoft Defender Antivirus in your Windows Security and [run scans](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus#run-a-scan-with-the-windows-security-app)</span></span>

[<span data-ttu-id="d4d9d-133">Artigo do Centro de Segurança do Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="d4d9d-133">Microsoft Defender security center article</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus)

[<span data-ttu-id="d4d9d-134">Cliente Web do Teams/aplicativo Web do Teams</span><span class="sxs-lookup"><span data-stu-id="d4d9d-134">Teams web client/teams web app</span></span>](../get-clients.md#web-client)

[<span data-ttu-id="d4d9d-135">Segurança e o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d4d9d-135">Security and Microsoft Teams</span></span>](https://docs.microsoft.com/microsoftteams/teams-security-guide)
