---
title: Habilitar Salas do Teams dispositivos para ingressar em reuniões de terceiros
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: sohailta
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
localization_priority: Normal
description: Este artigo discute como configurar sua organização e dispositivos Salas do Teams para dar suporte à junção de reuniões de terceiros à Cisco WebEx e zoom.
ms.openlocfilehash: ef14d1f342c6f2b34ad7c948a2688fa39a09801d
ms.sourcegitcommit: 8ad05b37c0b714adb069bc2503e88366ab75c57d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/07/2021
ms.locfileid: "52796685"
---
# <a name="enable-teams-room-devices-to-join-third-party-meetings"></a><span data-ttu-id="c04dc-103">Habilitar Teams dispositivos de sala para ingressar em reuniões de terceiros</span><span class="sxs-lookup"><span data-stu-id="c04dc-103">Enable Teams Room devices to join third-party meetings</span></span>

<span data-ttu-id="c04dc-104">Salas do Microsoft Teams dispositivos suportam uma experiência de toque único para ingressar em reuniões online de terceiros, também conhecidas como participação de convidados diretos.</span><span class="sxs-lookup"><span data-stu-id="c04dc-104">Microsoft Teams Rooms devices support a one-touch experience for joining third-party online meetings, also referred to as Direct guest join.</span></span> <span data-ttu-id="c04dc-105">Quando habilitado, você pode usar um dispositivo Salas do Teams para participar de reuniões hospedadas no Cisco WebEx e zoom da mesma forma que você pode participar de reuniões hospedadas no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c04dc-105">When enabled, you can use a Teams Rooms device to join meetings hosted on Cisco WebEx and Zoom just as easily as you can join meetings hosted in Microsoft Teams.</span></span>

<span data-ttu-id="c04dc-106">Antes de ingressar em reuniões de terceiros de um dispositivo Salas do Teams, você precisa fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c04dc-106">Before you can join third-party meetings from a Teams Rooms device, you need to do the following:</span></span>

1. <span data-ttu-id="c04dc-107">Configure a Salas do Teams caixa de correio de sala do Exchange Online do dispositivo para processar convites para reuniões de terceiros.</span><span class="sxs-lookup"><span data-stu-id="c04dc-107">Configure the Teams Rooms device's Exchange Online room mailbox to process invites for third-party meetings.</span></span>
2. <span data-ttu-id="c04dc-108">Certifique-se de que sua organização não tenha políticas que o impeçam de se conectar a serviços de reunião de terceiros.</span><span class="sxs-lookup"><span data-stu-id="c04dc-108">Make sure your organization doesn't have any policies that would prevent you from connecting to third-party meeting services.</span></span>
3. <span data-ttu-id="c04dc-109">Configure seus Salas do Teams para permitir reuniões de terceiros.</span><span class="sxs-lookup"><span data-stu-id="c04dc-109">Configure your Teams Rooms devices to allow third-party meetings.</span></span>

<span data-ttu-id="c04dc-110">As seções a seguir mostram como fazer cada uma dessas etapas.</span><span class="sxs-lookup"><span data-stu-id="c04dc-110">The following sections show you how to do each of these steps.</span></span>

## <a name="step-1-allow-calendar-invite-processing-for-third-party-meetings"></a><span data-ttu-id="c04dc-111">Etapa 1: Permitir o processamento de convites de calendário para reuniões de terceiros</span><span class="sxs-lookup"><span data-stu-id="c04dc-111">Step 1: Allow calendar invite processing for third-party meetings</span></span>

<span data-ttu-id="c04dc-112">A primeira coisa que você precisa fazer para habilitar uma experiência de junção de um toque a partir de um dispositivo salas de equipe é definir as regras de processamento de calendário para a caixa de correio de sala de Exchange Online do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c04dc-112">The first thing you need to do to enable a one-touch join experience from a Team Rooms device is set the calendar processing rules for the device's Exchange Online room mailbox.</span></span> <span data-ttu-id="c04dc-113">A caixa de correio de sala precisa permitir reuniões externas e manter o corpo e o assunto da mensagem para que ela possa ver a URL necessária para ingressar na reunião de terceiros.</span><span class="sxs-lookup"><span data-stu-id="c04dc-113">The room mailbox needs to allow external meetings and keep the message body and subject so it can see the URL needed to join the third-party meeting.</span></span> <span data-ttu-id="c04dc-114">Para definir essas opções de caixa de correio de sala usando o cmdlet [Set-CalendarProcessing,](/powershell/module/exchange/set-calendarprocessing?view=exchange-ps.) faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c04dc-114">To set these room mailbox options using the [Set-CalendarProcessing](/powershell/module/exchange/set-calendarprocessing?view=exchange-ps.) cmdlet, do the following:</span></span>

1. <span data-ttu-id="c04dc-115">Conexão para Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c04dc-115">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="c04dc-116">Para obter mais informações, consulte Conexão para Exchange Online [PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps) com autenticação básica ou Conexão para Exchange Online PowerShell usando autenticação [multifato](/powershell/exchange/mfa-connect-to-exchange-online-powershell?view=exchange-ps), dependendo do método de autenticação.</span><span class="sxs-lookup"><span data-stu-id="c04dc-116">For more information, see [Connect to Exchange Online PowerShell with Basic authentication](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps) or [Connect to Exchange Online PowerShell using multi-factor authentication](/powershell/exchange/mfa-connect-to-exchange-online-powershell?view=exchange-ps), depending on your authentication method.</span></span>

2. <span data-ttu-id="c04dc-117">Obter o Nome de Entidade de Usuário (UPN) da caixa de correio de sala se você não a conhece executando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="c04dc-117">Get the User Principal Name (UPN) of the room mailbox if you don't know it by running the following command:</span></span>

    ```powershell
    Get-Mailbox | Where {$_.RoomMailboxAccountEnabled -eq $True} | Format-Table Name, UserPrincipalName
    ```
    
3. <span data-ttu-id="c04dc-118">Encontre o nome da caixa de correio de sala associada ao dispositivo Salas do Teams e anote seu UPN.</span><span class="sxs-lookup"><span data-stu-id="c04dc-118">Find the name of the room mailbox associated with your Teams Rooms device and make note of its UPN.</span></span>

4. <span data-ttu-id="c04dc-119">Depois de encontrar o UPN da caixa de correio da sala, execute o seguinte comando.</span><span class="sxs-lookup"><span data-stu-id="c04dc-119">After you find the room mailbox's UPN, run the following command.</span></span> <span data-ttu-id="c04dc-120">Substitua `<UserPrincipalName>` pelo UPN da caixa de correio da sala:</span><span class="sxs-lookup"><span data-stu-id="c04dc-120">Replace `<UserPrincipalName>` with the room mailbox's UPN:</span></span>

    ```powershell
    Set-CalendarProcessing <UserPrincipalName> -ProcessExternalMeetingMessages $True -DeleteComments $False -DeleteSubject $False
    ```

<span data-ttu-id="c04dc-121">Saiba mais sobre [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="c04dc-121">Learn more about [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell?view=exchange-ps).</span></span>

## <a name="step-2-configure-office-365-threat-protection-and-link-rewrite"></a><span data-ttu-id="c04dc-122">Etapa 2: Configurar Office 365 Proteção contra Ameaças e regravar link</span><span class="sxs-lookup"><span data-stu-id="c04dc-122">Step 2: Configure Office 365 Threat Protection and link rewrite</span></span>

<span data-ttu-id="c04dc-123">Para habilitar a experiência de junção de um toque, as informações de link de junção de reunião da reunião de terceiros precisam estar presentes e habilitadas no convite da reunião.</span><span class="sxs-lookup"><span data-stu-id="c04dc-123">To enable the one-touch join experience, meeting join link information from the third-party meeting needs to be present and readable in the meeting invite.</span></span> <span data-ttu-id="c04dc-124">Se a sua organização usa o recurso de Proteção Avançada contra Ameaças [Cofre Links](/microsoft-365/security/office-365-security/atp-safe-links) ou se você usar uma solução de terceiros que verifica todas as URLs de entrada e de saída em busca de ameaças, ela pode alterar as URLs de participação da reunião e tornar a reunião irreconhecível pelo dispositivo Salas do Teams. Office 365</span><span class="sxs-lookup"><span data-stu-id="c04dc-124">If your organization uses the [Office 365 Advanced Threat Protection Safe Links](/microsoft-365/security/office-365-security/atp-safe-links) feature, or if you use a third-party solution that scans all incoming and outgoing URLs for threats, it may change the meeting join URLs and make the meeting unrecognizable by the Teams Rooms device.</span></span> <span data-ttu-id="c04dc-125">Para garantir que isso não aconteça, você precisa adicionar AS URL Cofre s do serviço de reunião de terceiros à lista de links "não reescrever" ou à lista de exceção de regravar URL de terceiros.</span><span class="sxs-lookup"><span data-stu-id="c04dc-125">To make sure this doesn't happen, you need to add the third-party meeting service's URLs to the ATP Safe Links "do not rewrite" list or the third-party URL rewrite exception list.</span></span>

<span data-ttu-id="c04dc-126">Para adicionar URLs de serviço de reunião de terceiros à lista de Links "não reescrever" da AT Cofre P, siga as etapas em Configurar uma lista de [URLs personalizadas](/microsoft-365/security/office-365-security/set-up-a-custom-do-not-rewrite-urls-list-with-atp?view=o365-worldwide)que não regravem usando o ATP Cofre Links .</span><span class="sxs-lookup"><span data-stu-id="c04dc-126">To add third-party meeting service URLs to the ATP Safe Links "do not rewrite" list, follow the steps in [Set up a custom do-not-rewrite URLs list using ATP Safe Links](/microsoft-365/security/office-365-security/set-up-a-custom-do-not-rewrite-urls-list-with-atp?view=o365-worldwide).</span></span> <span data-ttu-id="c04dc-127">Se você usar uma solução de terceiros, consulte as instruções para que essa solução adicione URLs à lista de exceção de reescrita de URL.</span><span class="sxs-lookup"><span data-stu-id="c04dc-127">If you use a third-party solution, refer to the instructions for that solution to add URLs to its URL rewrite exception list.</span></span>

<span data-ttu-id="c04dc-128">Aqui estão algumas entradas de exemplo que talvez você precise adicionar à sua lista de links da ATP Cofre "não reescrever" ou lista de exceção de regravar URL de terceiros:</span><span class="sxs-lookup"><span data-stu-id="c04dc-128">Here are some example entries that you may need to add to your ATP Safe Links "do not rewrite" list or third-party URL rewrite exception list:</span></span>

- <span data-ttu-id="c04dc-129">**Cisco WebEx**`*.webex.com*`</span><span class="sxs-lookup"><span data-stu-id="c04dc-129">**Cisco WebEx** `*.webex.com*`</span></span>
- <span data-ttu-id="c04dc-130">**Zoom** `*.zoom.us*` , `*.zoom.com*``*.zoomgov.com*`</span><span class="sxs-lookup"><span data-stu-id="c04dc-130">**Zoom** `*.zoom.us*`, `*.zoom.com*`, `*.zoomgov.com*`</span></span>

<span data-ttu-id="c04dc-131">Para uma lista completa de URLs para adicionar à sua lista de links da ATP Cofre "não reescrever" ou lista de exceção de regravar URL de terceiros, entre em contato com o provedor de serviços de reunião de terceiros de onde você deseja aceitar convites de reunião.</span><span class="sxs-lookup"><span data-stu-id="c04dc-131">For a complete list of URLs to add to your ATP Safe Links "do not rewrite" list or third-party URL rewrite exception list, contact the third-party meeting service provider you want to accept meeting invites from.</span></span> 

> [!CAUTION]
> <span data-ttu-id="c04dc-132">Adicione apenas URLs que você confia à sua lista de Cofre links "não reescreve" ou lista de exceção de regravações de URL de terceiros.</span><span class="sxs-lookup"><span data-stu-id="c04dc-132">Only add URLs that you trust to your ATP Safe Links "do not rewrite" list or third-party URL rewrite exception list.</span></span>

## <a name="step-3-enable-third-party-meetings-on-device"></a><span data-ttu-id="c04dc-133">Etapa 3: Habilitar reuniões de terceiros no dispositivo</span><span class="sxs-lookup"><span data-stu-id="c04dc-133">Step 3: Enable third-party meetings on device</span></span>

<span data-ttu-id="c04dc-134">A última etapa que você precisa fazer é permitir que cada dispositivo Salas do Teams participe de reuniões de terceiros.</span><span class="sxs-lookup"><span data-stu-id="c04dc-134">The last step you need to do is allow each Teams Rooms device to join third-party meetings.</span></span> <span data-ttu-id="c04dc-135">As reuniões de terceiros exigem um nome de usuário e um endereço de email para ingressar neles.</span><span class="sxs-lookup"><span data-stu-id="c04dc-135">Third-party meetings require a username and email address to join them.</span></span> <span data-ttu-id="c04dc-136">Se o nome de usuário e o endereço de email que você precisa usar for diferente da caixa de correio de sala do dispositivo, você precisará adicioná-los ao dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c04dc-136">If the username and email address that you need to use is different than the device's room mailbox, you need to add them to your device.</span></span> <span data-ttu-id="c04dc-137">Você pode fazer isso nas configurações do dispositivo ou no arquivo de configuração XML.</span><span class="sxs-lookup"><span data-stu-id="c04dc-137">You can do this in the device settings or in the XML config file.</span></span>

### <a name="use-device-settings"></a><span data-ttu-id="c04dc-138">Usar configurações de dispositivo</span><span class="sxs-lookup"><span data-stu-id="c04dc-138">Use device settings</span></span>

<span data-ttu-id="c04dc-139">Para configurar o Salas do Teams usando sua tela touchscreen, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c04dc-139">To configure the Teams Rooms device using its touchscreen, do the following:</span></span>

1. <span data-ttu-id="c04dc-140">No dispositivo Salas do Microsoft Teams, selecione **Mais ...**.</span><span class="sxs-lookup"><span data-stu-id="c04dc-140">On the Microsoft Teams Rooms device, select **More ...**.</span></span>
2. <span data-ttu-id="c04dc-141">Selecione **Configurações** e insira o nome de usuário e a senha do administrador do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c04dc-141">Select **Settings**, and then enter the device administrator username and password.</span></span>
3. <span data-ttu-id="c04dc-142">Vá até a **guia Reuniões** e selecione **Cisco WebEx,** **Zoom** ou ambos.</span><span class="sxs-lookup"><span data-stu-id="c04dc-142">Go to the **Meetings** tab and select **Cisco WebEx**, **Zoom**, or both.</span></span>
4. <span data-ttu-id="c04dc-143">Se você quiser participar de reuniões com o nome de usuário e o endereço de email associado à caixa de correio de sala, selecione **Participar com informações da sala.**</span><span class="sxs-lookup"><span data-stu-id="c04dc-143">If you want to join meetings with the username and email address associated with the room mailbox, select **Join with room info**.</span></span>
5. <span data-ttu-id="c04dc-144">Se você quiser participar de reuniões com um nome de usuário alternativo e endereço de email, selecione **Ingressar** com informações personalizadas e insira nome de usuário e endereço de email que você gostaria de usar.</span><span class="sxs-lookup"><span data-stu-id="c04dc-144">If you want to join meetings with an alternate username and email address, select **Join with custom info** and enter username and email address you'd like to use.</span></span>
6. <span data-ttu-id="c04dc-145">Selecione **Salvar e sair**.</span><span class="sxs-lookup"><span data-stu-id="c04dc-145">Select **Save and exit**.</span></span> <span data-ttu-id="c04dc-146">Seu dispositivo será reiniciado.</span><span class="sxs-lookup"><span data-stu-id="c04dc-146">Your device will restart.</span></span>

### <a name="use-the-skypesettingsxml-configuration-file"></a><span data-ttu-id="c04dc-147">Usar o arquivo SkypeSettings.xml configuração</span><span class="sxs-lookup"><span data-stu-id="c04dc-147">Use the SkypeSettings.xml configuration file</span></span>

<span data-ttu-id="c04dc-148">As configurações a seguir podem ser adicionadas ao `SkypeSettings.xml` arquivo localizado em `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` .</span><span class="sxs-lookup"><span data-stu-id="c04dc-148">The following settings can be added to the `SkypeSettings.xml` file located in `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState`.</span></span> <span data-ttu-id="c04dc-149">Para obter mais informações sobre o `SkypeSettings.xml` arquivo, consulte [Manage a Salas do Microsoft Teams console settings remotely with an XML configuration file](xml-config-file.md).</span><span class="sxs-lookup"><span data-stu-id="c04dc-149">For more information about the `SkypeSettings.xml` file, see [Manage a Microsoft Teams Rooms console settings remotely with an XML configuration file](xml-config-file.md).</span></span>

<span data-ttu-id="c04dc-150">Para habilitar reuniões do Cisco WebEx, de definir o `WebExMeetingsEnabled` elemento XML como **True**, da seguinte forma.</span><span class="sxs-lookup"><span data-stu-id="c04dc-150">To enable Cisco WebEx meetings, set the `WebExMeetingsEnabled` XML element to **True**, as follows.</span></span>

```xml
<WebExMeetingsEnabled>True</WebExMeetingsEnabled>
```

<span data-ttu-id="c04dc-151">Para habilitar reuniões do Zoom, de definir o `ZoomMeetingsEnabled` elemento XML como **True**, da seguinte forma.</span><span class="sxs-lookup"><span data-stu-id="c04dc-151">To enable Zoom meetings, set the `ZoomMeetingsEnabled` XML element to **True**, as follows.</span></span>

```xml
<ZoomMeetingsEnabled>True</ZoomMeetingsEnabled>
```

<span data-ttu-id="c04dc-152">Opcionalmente, você pode especificar um nome de usuário personalizado e um endereço de email para ingressar em reuniões de terceiros usando os seguintes elementos XML.</span><span class="sxs-lookup"><span data-stu-id="c04dc-152">You can optionally specify a custom username and email address to join third-party meetings using the following XML elements.</span></span> <span data-ttu-id="c04dc-153">Se os valores que você fornece não são válidos, o dispositivo Salas do Teams padrão para usar o nome de usuário da caixa de correio de sala e o endereço de email.</span><span class="sxs-lookup"><span data-stu-id="c04dc-153">If the values you provide aren't valid, the Teams Rooms device will default to use room mailbox username and email address.</span></span>

```xml
<UseCustomInfoForThirdPartyMeetings>true</UseCustomInfoForThirdPartyMeetings>

<CustomDisplayNameForThirdPartyMeetings>guestname</CustomDisplayNameForThirdPartyMeetings>

<CustomDisplayEmailForThirdPartyMeetings>guest@contoso.com</CustomDisplayEmailForThirdPartyMeetings>
```

> [!NOTE]
> <span data-ttu-id="c04dc-154">Para ingressar em uma reunião do Cisco WebEx a partir de um dispositivo Salas do Teams, a reunião da Cisco precisa ser hospedada no WebEx Meetings Pro usando o aplicativo WebEx cisco versão WBS 40.7 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="c04dc-154">To join a Cisco WebEx meeting from a Teams Rooms device, the Cisco meeting needs to be hosted in WebEx Meetings Pro using Cisco WebEx web application version WBS 40.7 or later.</span></span> 
