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
ms.openlocfilehash: 7a42c46cf9592c64676d153e1885357a4ee8ec7b
ms.sourcegitcommit: 48cb3cdd69558ec80f8f25f870b302a65280ce5a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/08/2020
ms.locfileid: "48389929"
---
# <a name="use-onedrive-for-business-and-sharepoint-or-stream-for-meeting-recordings"></a><span data-ttu-id="00ad5-103">Usar o OneDrive for Business e o SharePoint ou o Stream para gravações de reunião</span><span class="sxs-lookup"><span data-stu-id="00ad5-103">Use OneDrive for Business and SharePoint or Stream for meeting recordings</span></span>

> [!Note]
> <span data-ttu-id="00ad5-104">A mudança do Microsoft Stream para o OneDrive for Business e o Microsoft Office SharePoint Online para gravações de reunião será uma abordagem em fases.</span><span class="sxs-lookup"><span data-stu-id="00ad5-104">The change from using Microsoft Stream to OneDrive for Business and SharePoint for meeting recordings will be a phased approach.</span></span> <span data-ttu-id="00ad5-105">Na inicialização, os administradores de locatários podem escolher esta nova opção de fluxo de trabalho hoje e começará a ver gravações automáticas do OneDrive for Business e do SharePoint em outubro de 2020.</span><span class="sxs-lookup"><span data-stu-id="00ad5-105">At launch, tenant admins can choose this new workflow option today and will start seeing recordings auto-upload to OneDrive for Business and SharePoint in October 2020.</span></span> <span data-ttu-id="00ad5-106">Em novembro, você precisará se recusar se quiser continuar a usar o Stream, e algum tempo no início de 2021 exigiremos que todos os clientes usem o OneDrive for Business e o SharePoint para novas gravações de reunião.</span><span class="sxs-lookup"><span data-stu-id="00ad5-106">In November you'll have to opt-out if you want to continue using Stream, and some time in early 2021 we'll require all customers to use OneDrive for Business and SharePoint for new meeting recordings.</span></span>

<span data-ttu-id="00ad5-107">O Microsoft Teams tem um novo método para salvar gravações na reunião.</span><span class="sxs-lookup"><span data-stu-id="00ad5-107">Microsoft Teams has a new method for saving meeting recordings.</span></span> <span data-ttu-id="00ad5-108">Como a primeira fase de uma transição do fluxo clássico da Microsoft para o [novo fluxo](https://docs.microsoft.com/stream/streamnew/new-stream), esse método armazena gravações no Microsoft onedrive e no SharePoint no Microsoft 365 e oferece muitos benefícios.</span><span class="sxs-lookup"><span data-stu-id="00ad5-108">As the first phase of a transition from classic Microsoft Stream to the [new Stream](https://docs.microsoft.com/stream/streamnew/new-stream), this method stores recordings on Microsoft OneDrive and SharePoint in Microsoft 365 and offers many benefits.</span></span>

<span data-ttu-id="00ad5-109">As vantagens de usar o OneDrive for Business e o SharePoint para armazenar gravações incluem:</span><span class="sxs-lookup"><span data-stu-id="00ad5-109">The benefits of using OneDrive for Business and SharePoint for storing recordings include:</span></span>

- <span data-ttu-id="00ad5-110">Políticas de retenção para a gravação de reuniões do Team (TMR) (rótulos de autoretenção do S + C E5)</span><span class="sxs-lookup"><span data-stu-id="00ad5-110">Retention policies for Teams meeting recording (TMR) (S+C E5 autoretention labels)</span></span>
- <span data-ttu-id="00ad5-111">Beneficie-se do OneDrive for Business e do controle de informações do SharePoint</span><span class="sxs-lookup"><span data-stu-id="00ad5-111">Benefit from OneDrive for Business and SharePoint information governance</span></span>
- <span data-ttu-id="00ad5-112">Permissões e compartilhamento fáceis de definir</span><span class="sxs-lookup"><span data-stu-id="00ad5-112">Easy to set permissions and sharing</span></span>
- <span data-ttu-id="00ad5-113">Compartilhe gravações com convidados (usuários externos) apenas com compartilhamento explícito</span><span class="sxs-lookup"><span data-stu-id="00ad5-113">Share recordings with guests (external users) with explicit share only</span></span>
- <span data-ttu-id="00ad5-114">Fluxo de solicitação de acesso</span><span class="sxs-lookup"><span data-stu-id="00ad5-114">Request access flow</span></span>
- <span data-ttu-id="00ad5-115">Fornecer links compartilhados do OneDrive for Business e do SharePoint</span><span class="sxs-lookup"><span data-stu-id="00ad5-115">Provide OneDrive for Business and SharePoint shared links</span></span>
- <span data-ttu-id="00ad5-116">Maior cota</span><span class="sxs-lookup"><span data-stu-id="00ad5-116">Increased quota</span></span>
- <span data-ttu-id="00ad5-117">As gravações de reunião estão disponíveis mais rapidamente</span><span class="sxs-lookup"><span data-stu-id="00ad5-117">Meeting  recordings are available faster</span></span>
- <span data-ttu-id="00ad5-118">Suporte do locatário local para o **go**</span><span class="sxs-lookup"><span data-stu-id="00ad5-118">**Go local** tenant support</span></span>
- <span data-ttu-id="00ad5-119">Suporte a várias regiões – as gravações são armazenadas em uma região específica desse usuário</span><span class="sxs-lookup"><span data-stu-id="00ad5-119">Multi-geo support – recordings are stored in a region specific to that user</span></span>
- <span data-ttu-id="00ad5-120">Dê suporte a essa chave (BYOK)</span><span class="sxs-lookup"><span data-stu-id="00ad5-120">Bring your own key (BYOK) support</span></span>
- <span data-ttu-id="00ad5-121">Qualidade de transcrição aprimorada e atribuição de alto-falante</span><span class="sxs-lookup"><span data-stu-id="00ad5-121">Improved Transcript quality and speaker attribution</span></span>

<span data-ttu-id="00ad5-122">Há algumas limitações a serem consideradas:</span><span class="sxs-lookup"><span data-stu-id="00ad5-122">There are some limitations to consider:</span></span>

- <span data-ttu-id="00ad5-123">Haverá legendas e transcrições ocultas somente em inglês.</span><span class="sxs-lookup"><span data-stu-id="00ad5-123">There will be English-only closed captions and transcripts.</span></span>
- <span data-ttu-id="00ad5-124">Você não poderá pesquisar transcrições ou conteúdo.</span><span class="sxs-lookup"><span data-stu-id="00ad5-124">You won't be able to search transcripts or their content.</span></span>
- <span data-ttu-id="00ad5-125">Você não conseguirá editar as transcrições, mas poderá ativar/desativar legendas.</span><span class="sxs-lookup"><span data-stu-id="00ad5-125">You won’t be able to edit the transcripts, but you'll be able to toggle captions off/on.</span></span>
- <span data-ttu-id="00ad5-126">Você pode controlar com quem compartilha a gravação, mas não poderá bloquear pessoas com acesso compartilhado para baixar a gravação.</span><span class="sxs-lookup"><span data-stu-id="00ad5-126">You can control with whom you share the recording, but you won't be able to block people with shared access from downloading the recording.</span></span>
- <span data-ttu-id="00ad5-127">Você não receberá um email quando a gravação terminar de salvar, mas a gravação será exibida no chat de reunião quando ela terminar.</span><span class="sxs-lookup"><span data-stu-id="00ad5-127">You'll not get an email when the recording finishes saving, but the recording will appear in the meeting chat once it’s finished.</span></span> <span data-ttu-id="00ad5-128">Isso ocorrerá muito mais rapidamente do que no fluxo anteriormente</span><span class="sxs-lookup"><span data-stu-id="00ad5-128">This will happen much quicker than it did in Stream previously</span></span>

<span data-ttu-id="00ad5-129">Assista à "gravação na reunião" para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="00ad5-129">Watch "Meeting Recording" for more information.</span></span>

> [!VIDEO https://www.youtube.com/embed/8iol0KfCeL8]

## <a name="set-up-the-meeting-recording-option-for-onedrive-for-business-and-sharepoint"></a><span data-ttu-id="00ad5-130">Configurar a opção de gravação de reunião do OneDrive for Business e do SharePoint</span><span class="sxs-lookup"><span data-stu-id="00ad5-130">Set up the meeting recording option for OneDrive for Business and SharePoint</span></span>

1. <span data-ttu-id="00ad5-131">Instale o console de administração do PowerShell do Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="00ad5-131">Install the Skype For Business Online PowerShell admin console.</span></span>

    <span data-ttu-id="00ad5-132">a.</span><span class="sxs-lookup"><span data-stu-id="00ad5-132">a.</span></span> <span data-ttu-id="00ad5-133">Baixe o [Skype for Business online PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="00ad5-133">Download [Skype for Business Online PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide).</span></span>

    <span data-ttu-id="00ad5-134">b.</span><span class="sxs-lookup"><span data-stu-id="00ad5-134">b.</span></span> <span data-ttu-id="00ad5-135">Siga os prompts para instalá-lo.</span><span class="sxs-lookup"><span data-stu-id="00ad5-135">Follow the prompts to install it.</span></span>

    <span data-ttu-id="00ad5-136">c.</span><span class="sxs-lookup"><span data-stu-id="00ad5-136">c.</span></span> <span data-ttu-id="00ad5-137">Reinicie o computador.</span><span class="sxs-lookup"><span data-stu-id="00ad5-137">Restart your machine.</span></span>

2. <span data-ttu-id="00ad5-138">Iniciar o PowerShell como administrador</span><span class="sxs-lookup"><span data-stu-id="00ad5-138">Launch PowerShell as an admin</span></span>

3. <span data-ttu-id="00ad5-139">Importe o conector SkypeOnline e faça logon como administrador do teams.</span><span class="sxs-lookup"><span data-stu-id="00ad5-139">Import the SkypeOnline Connector and log in as a Teams admin.</span></span>

```PowerShell
  Import-Module SkypeOnlineConnector
  $sfbSession = New-CsOnlineSession
  Import-PSSession $sfbSession
```

4. <span data-ttu-id="00ad5-140">Use [set-csteamsmeetingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) para definir uma política de reunião do teams para fazer a transição do armazenamento de fluxo para ODSP.</span><span class="sxs-lookup"><span data-stu-id="00ad5-140">Use [set-csteamsmeetingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) to set a Teams Meeting Policy to transition from the Stream storage to ODSP.</span></span>

```PowerShell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
```

## <a name="opt-out-of-onedrive-for-business-and-sharepoint-to-continue-using-stream"></a><span data-ttu-id="00ad5-141">Recusar o OneDrive for Business e o SharePoint para continuar usando o Stream</span><span class="sxs-lookup"><span data-stu-id="00ad5-141">Opt out of OneDrive for Business and SharePoint to continue using Stream</span></span>

<span data-ttu-id="00ad5-142">Mesmo se uma política disser que está definida como **Stream**, ela pode não ser definida.</span><span class="sxs-lookup"><span data-stu-id="00ad5-142">Even if a policy says it's set to **Stream**, it might not be set.</span></span> <span data-ttu-id="00ad5-143">Geralmente, se a política não estiver definida, a configuração padrão será **Stream**.</span><span class="sxs-lookup"><span data-stu-id="00ad5-143">Typically, if the policy isn't set, then the default setting is **Stream**.</span></span> <span data-ttu-id="00ad5-144">No entanto, com essa nova alteração, se você quiser optar por usar o SharePoint ou o OneDrive, será necessário redefinir a política para **transmitir** para garantir que seja o padrão.</span><span class="sxs-lookup"><span data-stu-id="00ad5-144">However, with this new change, if you want to opt-out of using SharePoint or OneDrive, then you must reset the policy to **Stream** to ensure that it's the default.</span></span>

```PowerShell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "Stream"
```

## <a name="frequently-asked-questions"></a><span data-ttu-id="00ad5-145">Perguntas frequentes</span><span class="sxs-lookup"><span data-stu-id="00ad5-145">Frequently asked questions</span></span>

<span data-ttu-id="00ad5-146">**Onde a gravação da reunião será armazenada?**</span><span class="sxs-lookup"><span data-stu-id="00ad5-146">**Where will the meeting recording be stored?**</span></span>

- <span data-ttu-id="00ad5-147">Para reuniões não relacionadas ao canal, a gravação é armazenada em uma pasta chamada **gravações** que está no nível superior do onedrive que pertence à pessoa que iniciou a gravação da reunião.</span><span class="sxs-lookup"><span data-stu-id="00ad5-147">For non-Channel meetings, the recording is stored in a folder named **Recordings** that is at the top level of the OneDrive that belongs to the person who started the meeting recording.</span></span> <span data-ttu-id="00ad5-148">Exemplo</span><span class="sxs-lookup"><span data-stu-id="00ad5-148">Example:</span></span>

  <span data-ttu-id="00ad5-149"><i>onedrive for Business</i> / do gravador **Gravações**</span><span class="sxs-lookup"><span data-stu-id="00ad5-149"><i>recorder's OneDrive for Business</i>/**Recordings**</span></span>

- <span data-ttu-id="00ad5-150">Para reuniões de canal, a gravação é armazenada na biblioteca de documentação do site do teams em uma pasta chamada **gravações**.</span><span class="sxs-lookup"><span data-stu-id="00ad5-150">For Channel meetings, the recording is stored in the Teams site documentation library in a folder named **Recordings**.</span></span> <span data-ttu-id="00ad5-151">Exemplo</span><span class="sxs-lookup"><span data-stu-id="00ad5-151">Example:</span></span>

  <span data-ttu-id="00ad5-152"><i>Nome do Team-nome</i> / do canal **Documentos** / do **Gravações**</span><span class="sxs-lookup"><span data-stu-id="00ad5-152"><i>Teams name - Channel name</i>/**Documents**/**Recordings**</span></span>

<span data-ttu-id="00ad5-153">**Como faço para lidar com gravações de ex-funcionários?**</span><span class="sxs-lookup"><span data-stu-id="00ad5-153">**How do I handle recordings from former employees?**</span></span>

<span data-ttu-id="00ad5-154">Como os vídeos são como qualquer outro arquivo no OneDrive e no SharePoint, a manipulação da posse e da retenção após a publicação de um funcionário acompanhará o processo normal do [onedrive e do SharePoint]( https://docs.microsoft.com/onedrive/retention-and-deletion#the-onedrive-deletion-process).</span><span class="sxs-lookup"><span data-stu-id="00ad5-154">Since videos are just like any other file in OneDrive and SharePoint, handling ownership and retention after an employee leaves will follow the normal [OneDrive and SharePoint process]( https://docs.microsoft.com/onedrive/retention-and-deletion#the-onedrive-deletion-process).</span></span>

<span data-ttu-id="00ad5-155">**Quem tem as permissões para exibir a gravação da reunião?**</span><span class="sxs-lookup"><span data-stu-id="00ad5-155">**Who has the permissions to view the meeting recording?**</span></span>

- <span data-ttu-id="00ad5-156">Em reuniões não canalizadas, todos os convidados da reunião, exceto para usuários externos, receberão automaticamente um link compartilhado pessoalmente.</span><span class="sxs-lookup"><span data-stu-id="00ad5-156">For non-Channel meetings, all meeting invitees, except for external users, will automatically get a personally shared link.</span></span> <span data-ttu-id="00ad5-157">Os usuários externos precisarão ser explicitamente adicionados à lista compartilhada pelo organizador da reunião ou pela pessoa que iniciou a gravação da reunião.</span><span class="sxs-lookup"><span data-stu-id="00ad5-157">External users will need to be explicitly added to the shared list by the meeting organizer or the person who started the meeting recording.</span></span>

- <span data-ttu-id="00ad5-158">Para reuniões de canal, as permissões são herdadas da lista de proprietários e membros no canal.</span><span class="sxs-lookup"><span data-stu-id="00ad5-158">For Channel meetings, permissions are inherited from the owners and members list in the channel.</span></span>

<span data-ttu-id="00ad5-159">**Como eu posso gerenciar transcrições?**</span><span class="sxs-lookup"><span data-stu-id="00ad5-159">**How can I manage transcripts?**</span></span>

<span data-ttu-id="00ad5-160">Os clientes que optarem por esta visualização não terão legendas ocultas disponíveis em suas gravações de reunião do teams migradas para o OneDrive e o SharePoint.</span><span class="sxs-lookup"><span data-stu-id="00ad5-160">Customers opting in to this preview will not have closed captions available on their Teams Meeting Recordings that are migrated to OneDrive and SharePoint.</span></span><span data-ttu-id="00ad5-161">Estamos trabalhando para adicionar legendas, começando com legendas ocultas em inglês, para fazer gravações em reuniões em outubro de 2020.</span><span class="sxs-lookup"><span data-stu-id="00ad5-161">  We're working to add captioning, beginning with closed captions in English, to meeting recordings in October 2020.</span></span>

<span data-ttu-id="00ad5-162">As legendas ocultas estarão disponíveis em gravações de reunião do teams para clientes que optaram por permitir transcrições, conforme descrito em [gravações na nuvem do teams](cloud-recording.md)</span><span class="sxs-lookup"><span data-stu-id="00ad5-162">Closed captions will be available on Teams Meeting Recordings for customers who have opted in to allow transcripts as described in [Teams cloud recordings](cloud-recording.md)</span></span>

<span data-ttu-id="00ad5-163">As legendas ajudam a criar conteúdo inclusivo para visualizadores de todas as habilidades.</span><span class="sxs-lookup"><span data-stu-id="00ad5-163">Captions help create inclusive content for viewers of all abilities.</span></span> <span data-ttu-id="00ad5-164">Como proprietário, você pode ocultar legendas, embora a transcrição ainda esteja disponível no Teams, a menos que você exclua as legendas do teams.</span><span class="sxs-lookup"><span data-stu-id="00ad5-164">As an owner, you can hide captions, although the transcript will still be available on Teams unless you delete the captions from Teams.</span></span> <span data-ttu-id="00ad5-165">Veja [como ativar ou desativar gravações de reunião](cloud-recording.md#set-up-teams-cloud-meeting-recording-for-users-in-your-organization)</span><span class="sxs-lookup"><span data-stu-id="00ad5-165">See [how to turn on or off meeting recordings](cloud-recording.md#set-up-teams-cloud-meeting-recording-for-users-in-your-organization)</span></span>

<span data-ttu-id="00ad5-166">As legendas ocultas são suportadas para gravações de reunião do Team por 60 dias a partir de quando a reunião é gravada.</span><span class="sxs-lookup"><span data-stu-id="00ad5-166">Closed captions are supported for Teams meeting recordings for 60 days from when the meeting is recorded.</span></span>

<span data-ttu-id="00ad5-167">**Como a minha cota de armazenamento será afetada**</span><span class="sxs-lookup"><span data-stu-id="00ad5-167">**How will my storage quota be impacted**</span></span>

<span data-ttu-id="00ad5-168">A reunião de equipes que grava arquivos residem no OneDrive for Business e no SharePoint e está incluída na sua cota para esses serviços.</span><span class="sxs-lookup"><span data-stu-id="00ad5-168">Teams meeting recording files live in OneDrive for Business and SharePoint and are included in your quota for those services.</span></span> <span data-ttu-id="00ad5-169">Consulte [cota do SharePoint](https://docs.microsoft.com/sharepoint/sites/plan-site-maintenance-and-management#quotas) e [cota do onedrive for Business] ( https://docs.microsoft.com/onedrive/set-default-storage-space) .</span><span class="sxs-lookup"><span data-stu-id="00ad5-169">See [SharePoint quota](https://docs.microsoft.com/sharepoint/sites/plan-site-maintenance-and-management#quotas) and [OneDrive for Business quota] (https://docs.microsoft.com/onedrive/set-default-storage-space).</span></span>

<span data-ttu-id="00ad5-170">**Como faço para reproduzir uma gravação de reunião do teams?**</span><span class="sxs-lookup"><span data-stu-id="00ad5-170">**How can I play a Teams meeting recording?**</span></span>

<span data-ttu-id="00ad5-171">Seu vídeo será reproduzido no player de vídeo do OneDrive for Business ou do SharePoint, dependendo de onde você acessar o arquivo.</span><span class="sxs-lookup"><span data-stu-id="00ad5-171">Your video will play on the video player of OneDrive for Business or SharePoint depending on where you access the file.</span></span>

<span data-ttu-id="00ad5-172">**Se você planeja substituir a adição ao Stream, os vídeos existentes permanecerão como estão e por quanto tempo?**</span><span class="sxs-lookup"><span data-stu-id="00ad5-172">**If you plan on deprecating adding to Stream, will existing videos stay as is and for how long?**</span></span>

<span data-ttu-id="00ad5-173">O fluxo como uma plataforma não será preterido em breve.</span><span class="sxs-lookup"><span data-stu-id="00ad5-173">Stream as a platform won't be deprecated in the near future.</span></span> <span data-ttu-id="00ad5-174">Os vídeos que residem atualmente no fluxo permanecerão lá até começarmos a migrar.</span><span class="sxs-lookup"><span data-stu-id="00ad5-174">The videos that currently live in Stream will stay there until we start migrating.</span></span> <span data-ttu-id="00ad5-175">Após a migração, esses vídeos também serão migrados para o ODSP.</span><span class="sxs-lookup"><span data-stu-id="00ad5-175">Upon migration, those videos will be migrated to ODSP as well.</span></span> <span data-ttu-id="00ad5-176">Confira [aqui](https://docs.microsoft.com/stream/streamnew/classic-migration) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="00ad5-176">Check [here](https://docs.microsoft.com/stream/streamnew/classic-migration) for more information.</span></span>
