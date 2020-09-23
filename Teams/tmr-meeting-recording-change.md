---
title: Usar o OneDrive e o SharePoint para gravações de reunião
author: cichur
ms.author: v-cichur
ms.reviewer: hao.moy
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Saiba como alternar do fluxo para o armazenamento de gravação de reunião do SharePoint e do SharePoint para o OneDrive for Business no Microsoft Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 65c0d50686346b715ca7e10b455845927ff22341
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218402"
---
# <a name="use-onedrive-for-business-and-sharepoint-or-stream-for-meeting-recordings"></a><span data-ttu-id="9f451-103">Usar o OneDrive for Business e o SharePoint ou o Stream para gravações de reunião</span><span class="sxs-lookup"><span data-stu-id="9f451-103">Use OneDrive for Business and SharePoint or Stream for meeting recordings</span></span>

> [!Note]
> <span data-ttu-id="9f451-104">A alteração de usar o Microsoft Stream para o OneDrive for Business e o SharePoint para gravações de reunião será uma abordagem em fases.</span><span class="sxs-lookup"><span data-stu-id="9f451-104">The change from using Microsoft Stream to OneDrive for Business and SharePoint for meeting recordings will be a phased approach.</span></span> <span data-ttu-id="9f451-105">No lançamento, você poderá optar por se recusar a essa experiência, em novembro, será preciso recusar se quiser continuar a usar o Stream, e algum tempo no início do 2021 exigiremos que todos os clientes usem o OneDrive for Business e o SharePoint para novas gravações de reunião.</span><span class="sxs-lookup"><span data-stu-id="9f451-105">At launch you'll be able to opt-in to this experience, in November you'll have to opt-out if you want to continue using Stream, and some time in early 2021 we'll require all customers to use OneDrive for Business and SharePoint for new meeting recordings.</span></span>

<span data-ttu-id="9f451-106">O Microsoft Teams tem um novo método para salvar gravações na reunião.</span><span class="sxs-lookup"><span data-stu-id="9f451-106">Microsoft Teams has a new method for saving meeting recordings.</span></span> <span data-ttu-id="9f451-107">Como uma partida do Stream, o método usa o Microsoft OneDrive e o SharePoint no Microsoft 365 e oferece muitos benefícios:</span><span class="sxs-lookup"><span data-stu-id="9f451-107">As a departure from Stream, the method uses Microsoft OneDrive and SharePoint in Microsoft 365 and offers many benefits:</span></span>

<span data-ttu-id="9f451-108">As vantagens de usar o OneDrive for Business e o SharePoint para armazenar gravações incluem:</span><span class="sxs-lookup"><span data-stu-id="9f451-108">The benefits of using OneDrive for Business and SharePoint for storing recordings include:</span></span>

- <span data-ttu-id="9f451-109">Políticas de retenção para a gravação de reuniões do Team (TMR) (rótulos de autoretenção do S + C E5)</span><span class="sxs-lookup"><span data-stu-id="9f451-109">Retention policies for Teams meeting recording (TMR) (S+C E5 autoretention labels)</span></span>
- <span data-ttu-id="9f451-110">Beneficie-se do OneDrive for Business e do controle de informações do SharePoint</span><span class="sxs-lookup"><span data-stu-id="9f451-110">Benefit from OneDrive for Business and SharePoint information governance</span></span>
- <span data-ttu-id="9f451-111">Permissões e compartilhamento fáceis de definir</span><span class="sxs-lookup"><span data-stu-id="9f451-111">Easy to set permissions and sharing</span></span>
- <span data-ttu-id="9f451-112">Compartilhe gravações com convidados (usuários externos) apenas com compartilhamento explícito</span><span class="sxs-lookup"><span data-stu-id="9f451-112">Share recordings with guests (external users) with explicit share only</span></span>
- <span data-ttu-id="9f451-113">Fluxo de solicitação de acesso</span><span class="sxs-lookup"><span data-stu-id="9f451-113">Request access flow</span></span>
- <span data-ttu-id="9f451-114">Fornecer links compartilhados do OneDrive for Business e do SharePoint</span><span class="sxs-lookup"><span data-stu-id="9f451-114">Provide OneDrive for Business and SharePoint shared links</span></span>
- <span data-ttu-id="9f451-115">Maior cota</span><span class="sxs-lookup"><span data-stu-id="9f451-115">Increased quota</span></span>
- <span data-ttu-id="9f451-116">As gravações de reunião estão disponíveis mais rapidamente</span><span class="sxs-lookup"><span data-stu-id="9f451-116">Meeting  recordings are available faster</span></span>
- <span data-ttu-id="9f451-117">Suporte do locatário local para o **go**</span><span class="sxs-lookup"><span data-stu-id="9f451-117">**Go local** tenant support</span></span>
- <span data-ttu-id="9f451-118">Suporte a várias regiões – as gravações são armazenadas em uma região específica desse usuário</span><span class="sxs-lookup"><span data-stu-id="9f451-118">Multi-geo support – recordings are stored in a region specific to that user</span></span>
- <span data-ttu-id="9f451-119">Dê suporte a essa chave (BYOK)</span><span class="sxs-lookup"><span data-stu-id="9f451-119">Bring your own key (BYOK) support</span></span>
- <span data-ttu-id="9f451-120">Qualidade de transcrição aprimorada e atribuição de alto-falante</span><span class="sxs-lookup"><span data-stu-id="9f451-120">Improved Transcript quality and speaker attribution</span></span>

<span data-ttu-id="9f451-121">Há algumas limitações a serem consideradas:</span><span class="sxs-lookup"><span data-stu-id="9f451-121">There are some limitations to consider:</span></span>

- <span data-ttu-id="9f451-122">Haverá legendas e transcrições ocultas somente em inglês.</span><span class="sxs-lookup"><span data-stu-id="9f451-122">There will be English-only closed captions and transcripts.</span></span>
- <span data-ttu-id="9f451-123">Você não poderá pesquisar transcrições ou conteúdo.</span><span class="sxs-lookup"><span data-stu-id="9f451-123">You won't be able to search transcripts or their content.</span></span>
- <span data-ttu-id="9f451-124">Você não conseguirá editar as transcrições, mas poderá ativar/desativar legendas.</span><span class="sxs-lookup"><span data-stu-id="9f451-124">You won’t be able to edit the transcripts, but you'll be able to toggle captions off/on.</span></span>
- <span data-ttu-id="9f451-125">Você pode controlar com quem compartilha a gravação, mas não poderá bloquear pessoas com acesso compartilhado para baixar a gravação.</span><span class="sxs-lookup"><span data-stu-id="9f451-125">You can control with whom you share the recording, but you won't be able to block people with shared access from downloading the recording.</span></span>
- <span data-ttu-id="9f451-126">Você não receberá um email quando a gravação terminar de salvar, mas a gravação será exibida no chat de reunião quando ela terminar.</span><span class="sxs-lookup"><span data-stu-id="9f451-126">You'll not get an email when the recording finishes saving, but the recording will appear in the meeting chat once it’s finished.</span></span> <span data-ttu-id="9f451-127">Isso ocorrerá muito mais rapidamente do que no fluxo anteriormente</span><span class="sxs-lookup"><span data-stu-id="9f451-127">This will happen much quicker than it did in Stream previously</span></span>

<span data-ttu-id="9f451-128">Assista à "gravação na reunião" para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="9f451-128">Watch "Meeting Recording" for more information.</span></span> 

> [!VIDEO https://www.youtube.com/embed/8iol0KfCeL8] 

## <a name="set-up-the-meeting-recording-option-for-onedrive-for-business-and-sharepoint"></a><span data-ttu-id="9f451-129">Configurar a opção de gravação de reunião do OneDrive for Business e do SharePoint</span><span class="sxs-lookup"><span data-stu-id="9f451-129">Set up the meeting recording option for OneDrive for Business and SharePoint</span></span>

1. <span data-ttu-id="9f451-130">Instale o console de administração do PowerShell do Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="9f451-130">Install the Skype For Business Online PowerShell admin console.</span></span>

    <span data-ttu-id="9f451-131">a.</span><span class="sxs-lookup"><span data-stu-id="9f451-131">a.</span></span> <span data-ttu-id="9f451-132">Baixe o [Skype for Business online PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="9f451-132">Download [Skype for Business Online Powershell](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide).</span></span>

    <span data-ttu-id="9f451-133">b.</span><span class="sxs-lookup"><span data-stu-id="9f451-133">b.</span></span> <span data-ttu-id="9f451-134">Siga os prompts para instalá-lo.</span><span class="sxs-lookup"><span data-stu-id="9f451-134">Follow the prompts to install it.</span></span>

    <span data-ttu-id="9f451-135">c.</span><span class="sxs-lookup"><span data-stu-id="9f451-135">c.</span></span> <span data-ttu-id="9f451-136">Reinicie o computador.</span><span class="sxs-lookup"><span data-stu-id="9f451-136">Restart your machine.</span></span>

2. <span data-ttu-id="9f451-137">Iniciar o PowerShell como administrador</span><span class="sxs-lookup"><span data-stu-id="9f451-137">Launch PowerShell as an admin</span></span>

3. <span data-ttu-id="9f451-138">Importe o conector SkypeOnline e faça logon como administrador do teams.</span><span class="sxs-lookup"><span data-stu-id="9f451-138">Import the SkypeOnline Connector and log in as a Teams admin.</span></span>

```PowerShell
  Import-Module SkypeOnlineConnector
  $sfbSession = New-CsOnlineSession
  Import-PSSession $sfbSession
```

4. <span data-ttu-id="9f451-139">Use [set-csteamsmeetingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) para definir uma política de reunião do teams para fazer a transição do armazenamento de fluxo para ODSP.</span><span class="sxs-lookup"><span data-stu-id="9f451-139">Use [set-csteamsmeetingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) to set a Teams Meeting Policy to transition from the Stream storage to ODSP.</span></span>

```PowerShell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
```

## <a name="opt-out-of-onedrive-for-business-and-sharepoint-to-continue-using-stream"></a><span data-ttu-id="9f451-140">Recusar o OneDrive for Business e o SharePoint para continuar usando o Stream</span><span class="sxs-lookup"><span data-stu-id="9f451-140">Opt out of OneDrive for Business and SharePoint to continue using Stream</span></span>

<span data-ttu-id="9f451-141">Mesmo que uma política diga que já está definida como **Stream**, ela pode não ser definida.</span><span class="sxs-lookup"><span data-stu-id="9f451-141">Even if a policy says it’s already set to **Stream**, it might not be set.</span></span> <span data-ttu-id="9f451-142">Se for definido como Nothing, o padrão será Stream.</span><span class="sxs-lookup"><span data-stu-id="9f451-142">If it's set to nothing, then the default is Stream.</span></span> <span data-ttu-id="9f451-143">Se desejar recusar, você **deve** redefinir a política para **transmitir** para garantir que o fluxo seja o padrão.</span><span class="sxs-lookup"><span data-stu-id="9f451-143">If you want to opt-out, you **must** reset the policy to **Stream** to ensure that Stream is the default.</span></span>

```PowerShell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "Stream"
```

## <a name="frequently-asked-questions"></a><span data-ttu-id="9f451-144">Perguntas frequentes</span><span class="sxs-lookup"><span data-stu-id="9f451-144">Frequently asked questions</span></span>

<span data-ttu-id="9f451-145">**Onde a gravação da reunião será armazenada?**</span><span class="sxs-lookup"><span data-stu-id="9f451-145">**Where will the meeting recording be stored?**</span></span>

- <span data-ttu-id="9f451-146">Para reuniões não relacionadas ao canal, a gravação é armazenada em uma pasta chamada.</span><span class="sxs-lookup"><span data-stu-id="9f451-146">For non-Channel meetings, the recording is stored in a folder named.</span></span> <span data-ttu-id="9f451-147">Gravações \* \* que está no nível superior do OneDrive que pertence à pessoa que iniciou a gravação da reunião.</span><span class="sxs-lookup"><span data-stu-id="9f451-147">Recordings\*\* that is at the top level of the OneDrive that belongs to the person who started the meeting recording.</span></span> <span data-ttu-id="9f451-148">Exemplo</span><span class="sxs-lookup"><span data-stu-id="9f451-148">Example:</span></span>

  <span data-ttu-id="9f451-149"><i>onedrive for Business</i> / do gravador **Gravações**</span><span class="sxs-lookup"><span data-stu-id="9f451-149"><i>recorder's OneDrive for Business</i>/**Recordings**</span></span>

- <span data-ttu-id="9f451-150">Para reuniões de canal, a gravação é armazenada na biblioteca de documentação do site do teams em uma pasta chamada **gravações**.</span><span class="sxs-lookup"><span data-stu-id="9f451-150">For Channel meetings, the recording is stored in the Teams site documentation library in a folder named **Recordings**.</span></span> <span data-ttu-id="9f451-151">Exemplo</span><span class="sxs-lookup"><span data-stu-id="9f451-151">Example:</span></span>

  <span data-ttu-id="9f451-152"><i>Nome do Team-nome</i> / do canal **Documentos** / do **Gravações**</span><span class="sxs-lookup"><span data-stu-id="9f451-152"><i>Teams name - Channel name</i>/**Documents**/**Recordings**</span></span>

<span data-ttu-id="9f451-153">**Quem tem as permissões para exibir a gravação da reunião?**</span><span class="sxs-lookup"><span data-stu-id="9f451-153">**Who has the permissions to view the meeting recording?**</span></span>

- <span data-ttu-id="9f451-154">Em reuniões não canalizadas, todos os convidados da reunião, exceto para usuários externos, receberão automaticamente um link compartilhado pessoalmente.</span><span class="sxs-lookup"><span data-stu-id="9f451-154">For non-Channel meetings, all meeting invitees, except for external users, will automatically get a personally shared link.</span></span> <span data-ttu-id="9f451-155">Os usuários externos precisarão ser explicitamente adicionados à lista compartilhada pelo organizador da reunião ou pela pessoa que iniciou a gravação da reunião.</span><span class="sxs-lookup"><span data-stu-id="9f451-155">External users will need to be explicitly added to the shared list by the meeting organizer or the person who started the meeting recording.</span></span>

- <span data-ttu-id="9f451-156">Para reuniões de canal, as permissões são herdadas da lista de proprietários e membros no canal.</span><span class="sxs-lookup"><span data-stu-id="9f451-156">For Channel meetings, permissions are inherited from the owners and members list in the channel.</span></span>

<span data-ttu-id="9f451-157">**Como eu posso gerenciar transcrições?**</span><span class="sxs-lookup"><span data-stu-id="9f451-157">**How can I manage transcripts?**</span></span>

<span data-ttu-id="9f451-158">Os clientes que optarem por esta visualização não terão legendas ocultas disponíveis em suas gravações de reunião do teams migradas para o OneDrive e o SharePoint.</span><span class="sxs-lookup"><span data-stu-id="9f451-158">Customers opting in to this preview will not have closed captions available on their Teams Meeting Recordings that are migrated to OneDrive and SharePoint.</span></span><span data-ttu-id="9f451-159">Estamos trabalhando para adicionar legendas, começando com legendas ocultas em inglês, para fazer gravações em reuniões em outubro de 2020.</span><span class="sxs-lookup"><span data-stu-id="9f451-159">  We're working to add captioning, beginning with closed captions in English, to meeting recordings in October 2020.</span></span>

<span data-ttu-id="9f451-160">As legendas ocultas estarão disponíveis em gravações de reunião do teams para clientes que optaram por permitir transcrições, conforme descrito em [gravações na nuvem do teams](cloud-recording.md)</span><span class="sxs-lookup"><span data-stu-id="9f451-160">Closed captions will be available on Teams Meeting Recordings for customers who have opted in to allow transcripts as described in [Teams cloud recordings](cloud-recording.md)</span></span>

<span data-ttu-id="9f451-161">As legendas ajudam a criar conteúdo inclusivo para visualizadores de todas as habilidades.</span><span class="sxs-lookup"><span data-stu-id="9f451-161">Captions help create inclusive content for viewers of all abilities.</span></span> <span data-ttu-id="9f451-162">Como proprietário, você pode ocultar legendas, embora a transcrição ainda esteja disponível no Teams, a menos que você exclua as legendas do teams.</span><span class="sxs-lookup"><span data-stu-id="9f451-162">As an owner, you can hide captions, although the transcript will still be available on Teams unless you delete the captions from Teams.</span></span> <span data-ttu-id="9f451-163">Veja [como ativar ou desativar gravações de reunião](cloud-recording.md#set-up-teams-cloud-meeting-recording-for-users-in-your-organization)</span><span class="sxs-lookup"><span data-stu-id="9f451-163">See [how to turn on or off meeting recordings](cloud-recording.md#set-up-teams-cloud-meeting-recording-for-users-in-your-organization)</span></span>

<span data-ttu-id="9f451-164">As legendas ocultas são suportadas para gravações de reunião do Team por 60 dias a partir de quando a reunião é gravada.</span><span class="sxs-lookup"><span data-stu-id="9f451-164">Closed captions are supported for Teams meeting recordings for 60 days from when the meeting is recorded.</span></span>

<span data-ttu-id="9f451-165">**Como a minha cota de armazenamento será afetada**</span><span class="sxs-lookup"><span data-stu-id="9f451-165">**How will my storage quota be impacted**</span></span>

<span data-ttu-id="9f451-166">A reunião de equipes que grava arquivos residem no OneDrive for Business e no SharePoint e está incluída na sua cota para esses serviços.</span><span class="sxs-lookup"><span data-stu-id="9f451-166">Teams meeting recording files live in OneDrive for Business and SharePoint and are included in your quota for those services.</span></span> <span data-ttu-id="9f451-167">Consulte [cota do SharePoint](https://docs.microsoft.com/sharepoint/sites/plan-site-maintenance-and-management#quotas) e [cota do onedrive for Business] ( https://docs.microsoft.com/onedrive/set-default-storage-space) .</span><span class="sxs-lookup"><span data-stu-id="9f451-167">See [SharePoint quota](https://docs.microsoft.com/sharepoint/sites/plan-site-maintenance-and-management#quotas) and [OneDrive for Business quota] (https://docs.microsoft.com/onedrive/set-default-storage-space).</span></span>

<span data-ttu-id="9f451-168">**Como faço para reproduzir uma gravação de reunião do teams?**</span><span class="sxs-lookup"><span data-stu-id="9f451-168">**How can I play a Teams meeting recording?**</span></span>

<span data-ttu-id="9f451-169">Seu vídeo será reproduzido no player de vídeo do OneDrive for Business ou do SharePoint, dependendo de onde você acessar o arquivo.</span><span class="sxs-lookup"><span data-stu-id="9f451-169">Your video will play on the video player of OneDrive for Business or SharePoint depending on where you access the file.</span></span>
