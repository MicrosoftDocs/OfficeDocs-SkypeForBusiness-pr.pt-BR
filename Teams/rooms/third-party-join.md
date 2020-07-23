---
title: Habilitar dispositivos de salas de equipe para participar de reuniões de terceiros
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
description: Este artigo discute como configurar os dispositivos da sua organização e salas de equipe para dar suporte à reunião de terceiros de acordo com o Cisco WebEx e o zoom.
ms.openlocfilehash: 708fb7f9d243559a571b2b9016fab1e38aa63114
ms.sourcegitcommit: 3e5cac88911611c94c0330bf50af9c34db308cdf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/22/2020
ms.locfileid: "45372210"
---
# <a name="enable-teams-room-devices-to-join-third-party-meetings"></a><span data-ttu-id="bdc8a-103">Habilitar dispositivos da sala de equipe para participar de reuniões de terceiros</span><span class="sxs-lookup"><span data-stu-id="bdc8a-103">Enable Teams Room devices to join third-party meetings</span></span>

<span data-ttu-id="bdc8a-104">Os dispositivos de salas do Microsoft Teams dão suporte a uma experiência de toque único para a associação online de reuniões online de terceiros.</span><span class="sxs-lookup"><span data-stu-id="bdc8a-104">Microsoft Teams Rooms devices support a one-touch experience for joining third-party online meetings.</span></span> <span data-ttu-id="bdc8a-105">Quando habilitado, você pode usar um dispositivo de salas de equipe para ingressar em reuniões hospedadas no Cisco WebEx e fazer o zoom de<sup>1</sup> tão facilmente quanto você pode ingressar em reuniões hospedadas no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="bdc8a-105">When enabled, you can use a Teams Rooms device to join meetings hosted on Cisco WebEx and Zoom<sup>1</sup> just as easily as you can join meetings hosted in Microsoft Teams.</span></span>

<span data-ttu-id="bdc8a-106">Antes de poder ingressar em reuniões de terceiros a partir de um dispositivo de salas de equipe, você precisa fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="bdc8a-106">Before you can join third-party meetings from a Teams Rooms device, you need to do the following:</span></span>

1. <span data-ttu-id="bdc8a-107">Configurar a caixa de correio da sala do Exchange Online do dispositivo de salas de equipe para processar convites para reuniões de terceiros</span><span class="sxs-lookup"><span data-stu-id="bdc8a-107">Configure the Teams Rooms device's Exchange Online room mailbox to process invites for third-party meetings</span></span>
2. <span data-ttu-id="bdc8a-108">Verifique se a sua organização não tem nenhuma política que impeça você de se conectar a serviços de reunião de terceiros</span><span class="sxs-lookup"><span data-stu-id="bdc8a-108">Make sure your organization doesn't have any policies that would prevent you from connecting to third-party meeting services</span></span>
3. <span data-ttu-id="bdc8a-109">Configurar dispositivos de salas de equipe para permitir reuniões de terceiros</span><span class="sxs-lookup"><span data-stu-id="bdc8a-109">Configure your Teams Rooms devices to allow third-party meetings</span></span>

<span data-ttu-id="bdc8a-110">As seções a seguir mostram como executar cada uma dessas etapas.</span><span class="sxs-lookup"><span data-stu-id="bdc8a-110">The following sections show you how to do each of these steps.</span></span>

## <a name="step-1-allow-calendar-invite-processing-for-third-party-meetings"></a><span data-ttu-id="bdc8a-111">Etapa 1: permitir o processamento de convites de calendário para reuniões de terceiros</span><span class="sxs-lookup"><span data-stu-id="bdc8a-111">Step 1: Allow calendar invite processing for third-party meetings</span></span>

<span data-ttu-id="bdc8a-112">A primeira coisa que você precisa fazer para habilitar uma experiência de junção de um toque a partir de um dispositivo de salas de equipe é definir as regras de processamento de calendário para a caixa de correio da sala do Exchange Online do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="bdc8a-112">The first thing you need to do to enable a one-touch join experience from a Team Rooms device is set the calendar processing rules for the device's Exchange Online room mailbox.</span></span> <span data-ttu-id="bdc8a-113">A caixa de correio da sala precisa permitir reuniões externas e manter o corpo da mensagem e o assunto para que ele possa ver a URL necessária para ingressar na reunião de terceiros.</span><span class="sxs-lookup"><span data-stu-id="bdc8a-113">The room mailbox needs to allow external meetings and keep the message body and subject so it can see the URL needed to join the third-party meeting.</span></span> <span data-ttu-id="bdc8a-114">Para definir essas opções da caixa de correio de sala usando o cmdlet [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/set-calendarprocessing?view=exchange-ps.) , faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="bdc8a-114">To set these room mailbox options using the [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/set-calendarprocessing?view=exchange-ps.) cmdlet, do the following:</span></span>

1. <span data-ttu-id="bdc8a-115">Conecte-se ao PowerShell do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="bdc8a-115">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="bdc8a-116">Para obter mais informações, consulte [conectar ao PowerShell do Exchange Online com autenticação básica](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps) ou [conectar-se ao PowerShell do Exchange Online usando a autenticação multifator](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell?view=exchange-ps), dependendo do método de autenticação.</span><span class="sxs-lookup"><span data-stu-id="bdc8a-116">For more information, see [Connect to Exchange Online Powershell with Basic authentication](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps) or [Connect to Exchange Online PowerShell using multi-factor authentication](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell?view=exchange-ps), depending on your authentication method.</span></span>

2. <span data-ttu-id="bdc8a-117">Obtenha o nome UPN da caixa de correio da sala, se não souber, executando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="bdc8a-117">Get the User Principal Name (UPN) of the room mailbox if you don't know it by running the following command:</span></span>

    ```powershell
    Get-Mailbox | Where {$_.RoomMailboxAccountEnabled -eq $True} | Format-Table Name, UserPrincipalName
    ```
3. <span data-ttu-id="bdc8a-118">Localize o nome da caixa de correio da sala associada ao dispositivo de salas de equipe e anote seu UPN</span><span class="sxs-lookup"><span data-stu-id="bdc8a-118">Find the name of the room mailbox associated with your Teams Rooms device and make note of its UPN</span></span>

4. <span data-ttu-id="bdc8a-119">Depois de encontrar o UPN da caixa de correio da sala, execute o seguinte comando.</span><span class="sxs-lookup"><span data-stu-id="bdc8a-119">After you find the room mailbox's UPN, run the following command.</span></span> <span data-ttu-id="bdc8a-120">Substituir `<UserPrincipalName>` pelo UPN da caixa de correio da sala:</span><span class="sxs-lookup"><span data-stu-id="bdc8a-120">Replace `<UserPrincipalName>` with the room mailbox's UPN:</span></span>

    ```powershell
    Set-CalendarProcessing <UserPrincipalName> -ProcessExternalMeetingMessages $True -DeleteComments $False -DeleteSubject $False
    ```

<span data-ttu-id="bdc8a-121">Saiba mais sobre o [PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="bdc8a-121">Learn more about [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell?view=exchange-ps).</span></span>

## <a name="step-2-configure-office-365-threat-protection-and-link-rewrite"></a><span data-ttu-id="bdc8a-122">Etapa 2: configurar a proteção contra ameaças e a regravação de links do Office 365</span><span class="sxs-lookup"><span data-stu-id="bdc8a-122">Step 2: Configure Office 365 Threat Protection and link rewrite</span></span>

<span data-ttu-id="bdc8a-123">Para habilitar a experiência de junção de toque único, as informações do link de ingresso na reunião de terceiros devem estar presentes e legíveis no convite da reunião.</span><span class="sxs-lookup"><span data-stu-id="bdc8a-123">To enable the one-touch join experience, meeting join link information from the third-party meeting needs to be present and readable in the meeting invite.</span></span> <span data-ttu-id="bdc8a-124">Se a sua organização usa o recurso de [links seguros da proteção avançada contra ameaças do Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links)   ou se você usa uma solução de terceiros que examina todas as URLs de entrada e saída para ameaças, ela pode alterar as URLs de junção da reunião e torná-la irreconhecível para o dispositivo de salas de equipe.</span><span class="sxs-lookup"><span data-stu-id="bdc8a-124">If your organization uses the [Office 365 Advanced Threat Protection Safe Links](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links) feature, or if you use a third-party solution that scans all incoming and outgoing URLs for threats, it may change the meeting join URLs and make the meeting unrecognizable by the Teams Rooms device.</span></span> <span data-ttu-id="bdc8a-125">Para verificar se isso não acontece, você precisa adicionar as URLs de um serviço de reunião de terceiros à lista de links de segurança ATP "não reescrever" ou à lista de exceções de regravação de URL de terceiros.</span><span class="sxs-lookup"><span data-stu-id="bdc8a-125">To make sure this doesn't happen, you need to add the third-party meeting service's URLs to the ATP Safe Links "do not rewrite" list or the third-party URL rewrite exception list.</span></span>

<span data-ttu-id="bdc8a-126">Para adicionar URLs de serviços de reunião de terceiros à lista de links seguros ATP "não reescrever", siga as etapas em [Configurar uma lista de URLs do not Rewrite usando links de segurança ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-a-custom-do-not-rewrite-urls-list-with-atp?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="bdc8a-126">To add third-party meeting service URLs to the ATP Safe Links "do not rewrite" list, follow the steps in [Set up a custom do-not-rewrite URLs list using ATP Safe Links](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-a-custom-do-not-rewrite-urls-list-with-atp?view=o365-worldwide).</span></span> <span data-ttu-id="bdc8a-127">Se você usa uma solução de terceiros, consulte as instruções dessa solução para adicionar URLs à sua lista de exceções de regravação de URL.</span><span class="sxs-lookup"><span data-stu-id="bdc8a-127">If you use a third-party solution, refer to the instructions for that solution to add URLs to its URL rewrite exception list.</span></span>

<span data-ttu-id="bdc8a-128">Aqui estão alguns exemplos de entradas que talvez você precise adicionar à lista de exceções ATP "não reescrever" ou à lista de exceções de regravação de URL de terceiros:</span><span class="sxs-lookup"><span data-stu-id="bdc8a-128">Here are some example entries that you may need to add to your ATP Safe Links "do not rewrite" list or third-party URL rewrite exception list:</span></span>

- <span data-ttu-id="bdc8a-129">**Cisco WebEx**`*.webex.com*`</span><span class="sxs-lookup"><span data-stu-id="bdc8a-129">**Cisco WebEx** `*.webex.com*`</span></span>
- <span data-ttu-id="bdc8a-130">**Zoom** `*zoom.us*` , `*zoom.com*` ,`*zoomgov.com*`</span><span class="sxs-lookup"><span data-stu-id="bdc8a-130">**Zoom** `*zoom.us*`, `*zoom.com*`, `*zoomgov.com*`</span></span>

<span data-ttu-id="bdc8a-131">Para obter uma lista completa de URLs a serem adicionadas à lista de exceções ATP "não reescrever" ou à lista de exceções de terceiras URLs, entre em contato com o provedor de serviços de reunião de terceiros do qual você deseja aceitar os convites de reunião.</span><span class="sxs-lookup"><span data-stu-id="bdc8a-131">For a complete list of URLs to add to your ATP Safe Links "do not rewrite" list or third-party URL rewrite exception list, contact the third-party meeting service provider you want to accept meeting invites from.</span></span> 

> [!CAUTION]
> <span data-ttu-id="bdc8a-132">Adicione somente URLs confiáveis à lista de exceções ATP "não reescrever" ou à lista de exceções de regravação de URL de terceiros.</span><span class="sxs-lookup"><span data-stu-id="bdc8a-132">Only add URLs that you trust to your ATP Safe Links "do not rewrite" list or third-party URL rewrite exception list.</span></span>

## <a name="step-3-enable-third-party-meetings-on-device"></a><span data-ttu-id="bdc8a-133">Etapa 3: habilitar reuniões de terceiros no dispositivo</span><span class="sxs-lookup"><span data-stu-id="bdc8a-133">Step 3: Enable third-party meetings on device</span></span>

<span data-ttu-id="bdc8a-134">A última etapa que você precisa fazer é permitir que cada dispositivo de salas de equipe ingresse em reuniões de terceiros.</span><span class="sxs-lookup"><span data-stu-id="bdc8a-134">The last step you need to do is allow each Teams Rooms device to join third-party meetings.</span></span> <span data-ttu-id="bdc8a-135">Reuniões de terceiros exigem um nome de usuário e um endereço de e-mail para ingressar.</span><span class="sxs-lookup"><span data-stu-id="bdc8a-135">Third-party meetings require a username and email address to join them.</span></span> <span data-ttu-id="bdc8a-136">Se o nome de usuário e o endereço de email que você precisa usar forem diferentes da caixa de correio da sala do dispositivo, você precisará adicioná-los ao seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="bdc8a-136">If the username and email address that you need to use is different than the device's room mailbox, you need to add them to your device.</span></span> <span data-ttu-id="bdc8a-137">Você pode fazer isso nas configurações do dispositivo ou no arquivo XML de configuração.</span><span class="sxs-lookup"><span data-stu-id="bdc8a-137">You can do this in the device settings or in the XML config file.</span></span>

### <a name="use-device-settings"></a><span data-ttu-id="bdc8a-138">Usar as configurações do dispositivo</span><span class="sxs-lookup"><span data-stu-id="bdc8a-138">Use device settings</span></span>

<span data-ttu-id="bdc8a-139">Para configurar o dispositivo de salas de equipe usando o Touch Touch, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="bdc8a-139">To configure the Teams Rooms device using its touchscreen, do the following:</span></span>

1. <span data-ttu-id="bdc8a-140">No dispositivo salas do Microsoft Teams, selecione **mais..** .</span><span class="sxs-lookup"><span data-stu-id="bdc8a-140">On the Microsoft Teams Rooms device, select **More ...**</span></span>
2. <span data-ttu-id="bdc8a-141">Selecione **configurações**e, em seguida, digite o nome de usuário e a senha do administrador do dispositivo</span><span class="sxs-lookup"><span data-stu-id="bdc8a-141">Select **Settings**, and then enter the device administrator username and password</span></span>
3. <span data-ttu-id="bdc8a-142">Vá para a guia **reuniões**   e selecione **Cisco WebEx**, **zoom**<sup>1</sup>ou ambos</span><span class="sxs-lookup"><span data-stu-id="bdc8a-142">Go to the **Meetings** tab and select **Cisco WebEx**, **Zoom**<sup>1</sup>, or both</span></span>
4. <span data-ttu-id="bdc8a-143">Se você deseja ingressar em reuniões com o nome de usuário e o endereço de email associados à caixa de correio da sala, selecione **ingressar com informações de sala**</span><span class="sxs-lookup"><span data-stu-id="bdc8a-143">If you want to join meetings with the username and email address associated with the room mailbox, select **Join with room info**</span></span>
5. <span data-ttu-id="bdc8a-144">Se você quiser ingressar em reuniões com um nome de usuário e um endereço de email alternativos, selecione **ingressar com informações personalizadas** e insira o nome de usuário e o endereço de email que deseja usar</span><span class="sxs-lookup"><span data-stu-id="bdc8a-144">If you want to join meetings with an alternate username and email address, select **Join with custom info** and enter username and email address you'd like to use</span></span>
6. <span data-ttu-id="bdc8a-145">Selecione **salvar e sair**.</span><span class="sxs-lookup"><span data-stu-id="bdc8a-145">Select **Save and exit**.</span></span> <span data-ttu-id="bdc8a-146">Seu dispositivo será reiniciado.</span><span class="sxs-lookup"><span data-stu-id="bdc8a-146">Your device will restart.</span></span>

### <a name="use-the-skypesettingsxml-configuration-file"></a><span data-ttu-id="bdc8a-147">Usar o arquivo de configuração SkypeSettings.xml</span><span class="sxs-lookup"><span data-stu-id="bdc8a-147">Use the SkypeSettings.xml configuration file</span></span>

<span data-ttu-id="bdc8a-148">As configurações a seguir podem ser adicionadas ao `SkypeSettings.xml` arquivo localizado em `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` .</span><span class="sxs-lookup"><span data-stu-id="bdc8a-148">The following settings can be added to the `SkypeSettings.xml` file located in `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState`.</span></span> <span data-ttu-id="bdc8a-149">Para obter mais informações sobre o `SkypeSettings.xml` arquivo, consulte [gerenciar configurações de console de salas do Microsoft Teams remotamente com um arquivo de configuração XML](xml-config-file.md).</span><span class="sxs-lookup"><span data-stu-id="bdc8a-149">For more information about the `SkypeSettings.xml` file, see [Manage a Microsoft Teams Rooms console settings remotely with an XML configuration file](xml-config-file.md).</span></span>

<span data-ttu-id="bdc8a-150">Para habilitar reuniões Cisco WebEx, defina o `WebExMeetingsEnabled` elemento XML como **true**, da seguinte maneira.</span><span class="sxs-lookup"><span data-stu-id="bdc8a-150">To enable Cisco WebEx meetings, set the `WebExMeetingsEnabled` XML element to **True**, as follows.</span></span>

```xml
<WebExMeetingsEnabled>True</WebExMeetingsEnabled>
```

<span data-ttu-id="bdc8a-151">Para habilitar o zoom<sup>1</sup> reuniões, defina o `ZoomMeetingsEnabled` elemento XML como **verdadeiro**, da seguinte maneira.</span><span class="sxs-lookup"><span data-stu-id="bdc8a-151">To enable Zoom<sup>1</sup> meetings, set the `ZoomMeetingsEnabled` XML element to **True**, as follows.</span></span>

```xml
<ZoomMeetingsEnabled>True</ZoomMeetingsEnabled>
```

<span data-ttu-id="bdc8a-152">Opcionalmente, você pode especificar um nome de usuário e um endereço de email personalizados para ingressar em reuniões de terceiros usando os seguintes elementos XML.</span><span class="sxs-lookup"><span data-stu-id="bdc8a-152">You can optionally specify a custom username and email address to join third-party meetings using the following XML elements.</span></span> <span data-ttu-id="bdc8a-153">Se os valores fornecidos não forem válidos, o dispositivo de salas de equipe usará como padrão usar o nome de usuário e o endereço de email da caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="bdc8a-153">If the values you provide aren't valid, the Teams Rooms device will default to use room mailbox username and email address.</span></span>

```xml
<UseCustomInfoForThirdPartyMeetings>true</UseCustomInfoForThirdPartyMeetings>

<CustomDisplayNameForThirdPartyMeetings>guestname</CustomDisplayNameForThirdPartyMeetings>

<CustomDisplayEmailForThirdPartyMeetings>guest@contoso.com</CustomDisplayEmailForThirdPartyMeetings>
```

> [!NOTE]
> <span data-ttu-id="bdc8a-154">Para ingressar em uma reunião do Cisco WebEx a partir de um dispositivo de salas de equipe, a reunião da Cisco precisa ser hospedada usando a versão WBS 40,7 ou posterior do aplicativo Web Cisco WebEx.</span><span class="sxs-lookup"><span data-stu-id="bdc8a-154">To join Cisco WebEx meeting from a Teams Rooms device, the Cisco meeting needs to be hosted using Cisco WebEx web application version WBS 40.7 or later.</span></span>

<span data-ttu-id="bdc8a-155"><sup>1</sup> o zoom das reuniões de zoom só está disponível no momento para selecionar clientes de salas do Microsoft Teams com o programa de acesso à tecnologia (toque).</span><span class="sxs-lookup"><span data-stu-id="bdc8a-155"><sup>1</sup> Zoom meetings join is currently only available to select Microsoft Teams Rooms customers through Technology Access Program (TAP).</span></span>
