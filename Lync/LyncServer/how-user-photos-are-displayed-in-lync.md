---
title: Como as fotos do usuário são exibidas no Lync
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: How user photos are displayed in Lync
ms:assetid: b44a364d-a1d2-4d45-b27a-b5f77775e233
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn783119(v=OCS.15)
ms:contentKeyID: 62835297
ms.date: 08/27/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 88d6f6f6f5578994831fd15329988d963a295832
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755435"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="how-user-photos-are-displayed-in-lync"></a><span data-ttu-id="ece47-102">Como as fotos do usuário são exibidas no Lync</span><span class="sxs-lookup"><span data-stu-id="ece47-102">How user photos are displayed in Lync</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ece47-103">_**Última modificação do tópico:** 2014-08-25_</span><span class="sxs-lookup"><span data-stu-id="ece47-103">_**Topic Last Modified:** 2014-08-25_</span></span>

<span data-ttu-id="ece47-104">**Resumo:** As fotos do usuário exibidas no cliente do Lync podem ser diferentes dependendo de qual recurso do Lync você estiver usando, como quando estiver em uma conferência ou em um chat de mensagens instantâneas.</span><span class="sxs-lookup"><span data-stu-id="ece47-104">**Summary:** User photos displayed in Lync client can be different depending on which Lync feature you are using, such as when in a conference or an IM chat.</span></span>

<span data-ttu-id="ece47-105">O Lync 2010 introduziu a capacidade de incluir uma foto com seu perfil do Lync que é exibido para outros usuários do Lync.</span><span class="sxs-lookup"><span data-stu-id="ece47-105">Lync 2010 introduced the ability to include a photo with your Lync profile that is displayed to other Lync users.</span></span> <span data-ttu-id="ece47-106">Você também pode escolher se deseja ou não exibir fotos para seus contatos no cliente Lync.</span><span class="sxs-lookup"><span data-stu-id="ece47-106">You can also choose whether or not to display photos for your contacts in Lync client.</span></span> <span data-ttu-id="ece47-107">No Lync 2013, suporte para fotos de alta resolução para usuários.</span><span class="sxs-lookup"><span data-stu-id="ece47-107">In Lync 2013, support for high-resolution photos for users.</span></span> <span data-ttu-id="ece47-108">Este tópico descreve como o cliente do Lync Obtém e exibe fotos do usuário, onde elas estão armazenadas, as limitações de cada fonte de imagem e como as fotos do usuário são usadas por diferentes serviços do Lync.</span><span class="sxs-lookup"><span data-stu-id="ece47-108">This topic describes how Lync client gets and displays user photos, where the images are stored, the limitations for each image source, and how user photos are used by different Lync services.</span></span>

<div>

## <a name="planning-considerations"></a><span data-ttu-id="ece47-109">Considerações de planejamento</span><span class="sxs-lookup"><span data-stu-id="ece47-109">Planning considerations</span></span>

<span data-ttu-id="ece47-110">Você deve considerar o seguinte ao planejar a implementação do suporte para fotos do usuário.</span><span class="sxs-lookup"><span data-stu-id="ece47-110">You should consider the following when planning to implement support for user photos.</span></span>

  - <span data-ttu-id="ece47-111">O suporte a foto de usuário de alta definição exige que a caixa de correio do usuário esteja localizada no Exchange 2013 e a conta de usuário do Lync seja no pool do Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="ece47-111">High-definition user photo support requires that the user’s mailbox be located on Exchange 2013 and the Lync user account to be in Lync 2013 pool.</span></span>

  - <span data-ttu-id="ece47-112">Fotos de usuário de alta definição têm suporte apenas em um ambiente onde o Lync Server 2013 e o Exchange 2013 são usados.</span><span class="sxs-lookup"><span data-stu-id="ece47-112">High-definition user photos are supported only in an environment where both Lync Server 2013 and Exchange 2013 are used.</span></span>

  - <span data-ttu-id="ece47-113">Os usuários com caixas de correio no Exchange 2010 sempre usarão o atributo **ThumbNailPhoto** do AD DS como a origem da foto do usuário.</span><span class="sxs-lookup"><span data-stu-id="ece47-113">Users with Mailboxes on Exchange 2010 will always use the **thumbnailPhoto** attribute from AD DS as the source for their user photo.</span></span>

  - <span data-ttu-id="ece47-114">Uma foto de usuário armazenada como o atributo **ThumbNailPhoto** do AD DS não será exibida para contatos externos/federados.</span><span class="sxs-lookup"><span data-stu-id="ece47-114">A user photo stored as the **thumbnailPhoto** attribute from AD DS will not be displayed to external / federated contacts.</span></span>

  - <span data-ttu-id="ece47-115">Se as fotos para contatos de usuários estiverem armazenadas no AD DS, o arquivo de imagem usado será limitado a 96 × 96 pixels e não mais do que 100 KB de tamanho de arquivo.</span><span class="sxs-lookup"><span data-stu-id="ece47-115">If the photos for user contacts are stored in AD DS, the image file used is limited to 96×96 pixels and no more than 100 KB file size.</span></span>

  - <span data-ttu-id="ece47-116">Se a conectividade entre o Lync Server e o Exchange Server for perdida, o **ThumbNailPhoto** de baixa resolução do usuário do AD DS será exibido e somente para usuários internos.</span><span class="sxs-lookup"><span data-stu-id="ece47-116">If connectivity between Lync Server and Exchange Server is lost, the user’s low resolution **thumbnailPhoto** from AD DS will be displayed, and to internal users only.</span></span>

  - <span data-ttu-id="ece47-117">As fotos do usuário de alta resolução são exibidas nas reuniões do Lync 2013 quando um alto-falante ativo não tem vídeo habilitado.</span><span class="sxs-lookup"><span data-stu-id="ece47-117">High-resolution user photos are displayed in Lync 2013 meetings when an active speaker does not have video enabled.</span></span> <span data-ttu-id="ece47-118">Além disso, mover o mouse sobre a foto em miniatura na Galeria exibirá a foto de alta resolução.</span><span class="sxs-lookup"><span data-stu-id="ece47-118">Also, moving the mouse over thumbnail photo in the gallery will display the high-resolution photo.</span></span>

</div>

<div>

## <a name="user-photos-in-lync-2010"></a><span data-ttu-id="ece47-119">Fotos do usuário no Lync 2010</span><span class="sxs-lookup"><span data-stu-id="ece47-119">User Photos in Lync 2010</span></span>

<span data-ttu-id="ece47-120">No cliente do Lync 2010, você pode escolher entre duas opções para exibir uma foto para seu perfil, **imagem corporativa padrão** e **Mostrar imagem de um endereço da Web**.</span><span class="sxs-lookup"><span data-stu-id="ece47-120">In the Lync 2010 client, you can choose from two options to display a photo for your profile, **Default corporate picture** and **Show picture from a web address**.</span></span>

<div>

## <a name="default-corporate-picture"></a><span data-ttu-id="ece47-121">Imagem empresarial padrão</span><span class="sxs-lookup"><span data-stu-id="ece47-121">Default corporate picture</span></span>

<span data-ttu-id="ece47-122">Quando você escolhe a opção **padrão de imagem corporativa** , o Lync Obtém a foto exibida para você nos serviços de domínio do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ece47-122">When you choose the **Default corporate picture** option, Lync gets the photo displayed for you from Active Directory Domain Services.</span></span> <span data-ttu-id="ece47-123">A imagem usada é a imagem definida como o valor do atributo **ThumbNailPhoto** nos serviços de domínio do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ece47-123">The image used is the image defined as the value for the **thumbnailPhoto** attribute in Active Directory Domain Services.</span></span> <span data-ttu-id="ece47-124">Este é o mesmo arquivo usado pelo Exchange para exibir imagens no Outlook.</span><span class="sxs-lookup"><span data-stu-id="ece47-124">This is the same file that is used by Exchange to display images in Outlook.</span></span>

<span data-ttu-id="ece47-125">As considerações para o uso de imagens de serviços de domínio do Active Directory incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="ece47-125">Considerations for using images from Active Directory Domain Services include the following:</span></span>

  - <span data-ttu-id="ece47-126">Somente imagens com dimensões até 96 pixels por 96 pixels são suportadas.</span><span class="sxs-lookup"><span data-stu-id="ece47-126">Only images with dimensions up to 96 pixels by 96 pixels are supported.</span></span> <span data-ttu-id="ece47-127">O tamanho do arquivo da imagem está limitado a 100 KB.</span><span class="sxs-lookup"><span data-stu-id="ece47-127">The file size for the image is limited to 100 KB.</span></span>

  - <span data-ttu-id="ece47-128">Por padrão, os usuários podem alterar a imagem usada para o atributo **ThumbNailPhoto** , embora não diretamente pelo cliente do Lync.</span><span class="sxs-lookup"><span data-stu-id="ece47-128">By default, users are able to change the image used for the **thumbnailPhoto** attribute, though not directly through Lync client.</span></span> <span data-ttu-id="ece47-129">Você pode desabilitá-lo por meio dos serviços de domínio do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ece47-129">You can disable this through Active Directory Domain Services.</span></span>

  - <span data-ttu-id="ece47-130">As imagens armazenadas nos serviços de domínio do Active Directory não são exibidas para os contatos externos à sua organização, mesmo que sejam contatos federados.</span><span class="sxs-lookup"><span data-stu-id="ece47-130">Images stored in Active Directory Domain Services are not displayed to contacts external to your organization, even if they are federated contacts.</span></span>

  - <span data-ttu-id="ece47-131">Em grandes organizações, armazenar e recuperar as imagens de um grande número de usuários pode impactar o tamanho e o desempenho do banco de dados dos serviços de domínio do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ece47-131">In large organizations, storing and retrieving the images for large numbers of users may impact the Active Directory Domain Services database size and performance.</span></span>

  - <span data-ttu-id="ece47-132">As dimensões de imagem limitada e o tamanho do arquivo significam que apenas imagens de baixa resolução podem ser usadas.</span><span class="sxs-lookup"><span data-stu-id="ece47-132">The limited image dimensions and file size mean that only low resolution images can be used.</span></span>

<div>

## <a name="how-users-manage-their-user-photos-in-active-directory-domain-services"></a><span data-ttu-id="ece47-133">Como os usuários gerenciam suas fotos de usuário nos serviços de domínio do Active Directory</span><span class="sxs-lookup"><span data-stu-id="ece47-133">How users manage their user photos in Active Directory Domain Services</span></span>

<span data-ttu-id="ece47-134">O usuário não pode alterar a imagem usada em seu perfil de serviços de domínio do Active Directory diretamente através do cliente Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="ece47-134">User cannot change the image used in their Active Directory Domain Services profile directly through Lync 2010 client.</span></span> <span data-ttu-id="ece47-135">Eles podem usar uma das seguintes opções para fazer isso, se disponíveis:</span><span class="sxs-lookup"><span data-stu-id="ece47-135">They can use one of the following options to do so, if available:</span></span>

  - <span data-ttu-id="ece47-136">**SharePoint Server**     Os usuários podem carregar uma foto em "My site" em um SharePoint Server e, em seguida, [Configurar a sincronização de perfil no SharePoint](https://go.microsoft.com/fwlink/p/?linkid=507466) para sincronizar a foto com o atributo **ThumbNailPhoto** nos serviços de domínio do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ece47-136">**SharePoint Server**   Users can upload a photo to ‘My Site’ on a SharePoint Server and then [configure profile synchronization in SharePoint](https://go.microsoft.com/fwlink/p/?linkid=507466) to synchronize the photo to the **thumbnailPhoto** attribute in Active Directory Domain Services.</span></span>

  - <span data-ttu-id="ece47-137">**Foto armazenada em URL**     publicamente acessível Os usuários podem configurar sua foto de usuário especificando uma URL publicamente acessível para a imagem que eles desejam usar.</span><span class="sxs-lookup"><span data-stu-id="ece47-137">**Photo stored on publicly accessible URL**   Users can configure their user photo specifying a publicly accessible URL for the image that they want to use.</span></span> <span data-ttu-id="ece47-138">A imagem deve estar publicamente acessível sem uma senha.</span><span class="sxs-lookup"><span data-stu-id="ece47-138">The image must be publicly accessible without a password.</span></span> <span data-ttu-id="ece47-139">A imagem armazenada no endereço da Web especificado é transferida para outros usuários por meio da categoria cartão de visita nas informações de presença.</span><span class="sxs-lookup"><span data-stu-id="ece47-139">The image stored at the specified web address is transferred to other users through the contact card category in the presence information.</span></span> <span data-ttu-id="ece47-140">Quando o cliente do Lync precisa exibir uma foto do usuário, ele recupera a imagem do endereço da Web especificado.</span><span class="sxs-lookup"><span data-stu-id="ece47-140">When Lync client needs to display a user photo, it retrieves the image from the specified web address.</span></span>

  - <span data-ttu-id="ece47-141">**Cmdlets do Exchange 2010 para Windows PowerShell**     Os administradores podem executar o cmdlet [Import-RecipientDataProperty](https://go.microsoft.com/fwlink/p/?linkid=507468) no Shell de gerenciamento do Exchange 2010 para gerenciar o atributo **ThumbNailPhoto** .</span><span class="sxs-lookup"><span data-stu-id="ece47-141">**Exchange 2010 cmdlets for Windows PowerShell**   Administrators can run the [Import-RecipientDataProperty](https://go.microsoft.com/fwlink/p/?linkid=507468) cmdlet in the Exchange 2010 Management Shell in to manage the **thumbnailPhoto** attribute.</span></span> <span data-ttu-id="ece47-142">Quando as imagens são importadas com os cmdlets do Exchange 2010, o tamanho do arquivo é limitado a 10 KB.</span><span class="sxs-lookup"><span data-stu-id="ece47-142">When images are imported with Exchange 2010 cmdlets, the file size is limited to 10 KB.</span></span>

  - <span data-ttu-id="ece47-143">**Ferramentas**     de terceiros Os usuários podem carregar apenas suas próprias fotos para o atributo **ThumbNailPhoto** .</span><span class="sxs-lookup"><span data-stu-id="ece47-143">**Third Party tools**   Users can upload only their own photo to for the **thumbnailPhoto** attribute.</span></span>

</div>

</div>

<div>

## <a name="show-a-picture-from-a-web-address"></a><span data-ttu-id="ece47-144">Exibir uma imagem de um endereço Web</span><span class="sxs-lookup"><span data-stu-id="ece47-144">Show a picture from a web address</span></span>

<span data-ttu-id="ece47-145">Quando você escolhe a opção **mostrar uma imagem de um endereço da Web** , o Lync Obtém a imagem no endereço inserido e a exibe para sua foto do usuário no Lync.</span><span class="sxs-lookup"><span data-stu-id="ece47-145">When you choose the **Show a picture from a web address** option, Lync gets the image at the address you enter and displays it for your user photo in Lync.</span></span>

<span data-ttu-id="ece47-146">As considerações para usar imagens de um endereço da Web incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="ece47-146">Considerations for using images from a web address include the following:</span></span>

  - <span data-ttu-id="ece47-147">Os limites de tamanho de arquivo são determinados pelo atributo **MaxPhotoSizeKB** na política de cliente, definido com o cmdlet [New-CsClientPolicy](https://go.microsoft.com/fwlink/p/?linkid=507463) .</span><span class="sxs-lookup"><span data-stu-id="ece47-147">File size limits are determined by the **MaxPhotoSizeKB** attribute in the client policy, defined with the [New-CsClientPolicy](https://go.microsoft.com/fwlink/p/?linkid=507463) cmdlet.</span></span> <span data-ttu-id="ece47-148">O limite de tamanho padrão é 30 KB.</span><span class="sxs-lookup"><span data-stu-id="ece47-148">The default size limit is 30 KB.</span></span> <span data-ttu-id="ece47-149">O valor máximo é 100 KB.</span><span class="sxs-lookup"><span data-stu-id="ece47-149">The maximum value is 100 KB.</span></span> <span data-ttu-id="ece47-150">Não há restrição na resolução da imagem, mas se você tentar usar um arquivo de imagem que excede o limite de tamanho, ele não será baixado para os clientes do Lync.</span><span class="sxs-lookup"><span data-stu-id="ece47-150">There is no restriction on the resolution of the image, but if you try to use an image file that exceeds the size limit it will not be downloaded to Lync clients.</span></span> <span data-ttu-id="ece47-151">Você pode definir o valor como 0 para desabilitar a utilização de todas as fotos do usuário no Lync.</span><span class="sxs-lookup"><span data-stu-id="ece47-151">You can set the value to 0 to disable all user photos from being used in Lync.</span></span>

  - <span data-ttu-id="ece47-152">As fotos de usuários de um endereço da Web podem ser vistas por contatos externos federados.</span><span class="sxs-lookup"><span data-stu-id="ece47-152">User photos from a web address can be seen by external federated contacts.</span></span>

</div>

<div>

## <a name="managing-users-photo-with-client-policy-cmdlets"></a><span data-ttu-id="ece47-153">Gerenciando fotos do usuário com cmdlets de política de cliente</span><span class="sxs-lookup"><span data-stu-id="ece47-153">Managing user’s photo with Client Policy cmdlets</span></span>

<span data-ttu-id="ece47-154">No Lync Server 2010, as configurações de política do cliente são configuradas com os cmdlets CsClientPolicy.</span><span class="sxs-lookup"><span data-stu-id="ece47-154">In Lync Server 2010, client policy settings are configured with the CsClientPolicy cmdlets.</span></span> <span data-ttu-id="ece47-155">As configurações de política configuradas são enviadas aos clientes por meio do provisionamento em banda.</span><span class="sxs-lookup"><span data-stu-id="ece47-155">The configured policy settings are sent to clients through in-band provisioning.</span></span> <span data-ttu-id="ece47-156">Os dois parâmetros dos cmdlets CsClientPolicy que determinam a experiência de foto do usuário são **DisplayPhoto** e **MaxPhotoSizeKB**.</span><span class="sxs-lookup"><span data-stu-id="ece47-156">The two parameters of the CsClientPolicy cmdlets that determine the user photo experience are **DisplayPhoto** and **MaxPhotoSizeKB**.</span></span> <span data-ttu-id="ece47-157">O parâmetro de provisionamento em banda correspondente para **DisplayPhoto** e **MaxPhotoSizeKB** é chamado de **fotousage**.</span><span class="sxs-lookup"><span data-stu-id="ece47-157">The corresponding in-band provisioning parameter for **DisplayPhoto** and **MaxPhotoSizeKB** is named **PhotoUsage**.</span></span> <span data-ttu-id="ece47-158">Os valores para o parâmetro **fotousage** são enviados aos clientes por meio do **endpointConfiguration** **Provision**.</span><span class="sxs-lookup"><span data-stu-id="ece47-158">Values for the **PhotoUsage** parameter are send to clients through the **endpointConfiguration** **provisionGroup**.</span></span> <span data-ttu-id="ece47-159">Confira [visão geral das políticas e configurações do cliente](https://go.microsoft.com/fwlink/?linkid=507470) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="ece47-159">See [Overview of Client Policies and Settings](https://go.microsoft.com/fwlink/?linkid=507470) for more information.</span></span>

<span data-ttu-id="ece47-160">O valor do parâmetro **DisplayPhoto** determina a origem da imagem de foto do usuário.</span><span class="sxs-lookup"><span data-stu-id="ece47-160">The **DisplayPhoto** parameter value determines the source of the user's photo image.</span></span> <span data-ttu-id="ece47-161">Os valores com suporte estão incluídos na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="ece47-161">The supported values are included in the following table.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ece47-162">Valor do parâmetro DisplayPhoto</span><span class="sxs-lookup"><span data-stu-id="ece47-162">DisplayPhoto parameter value</span></span></th>
<th><span data-ttu-id="ece47-163">Origem da imagem</span><span class="sxs-lookup"><span data-stu-id="ece47-163">Image source</span></span></th>
<th><span data-ttu-id="ece47-164">Configurações do cliente Lync 2010</span><span class="sxs-lookup"><span data-stu-id="ece47-164">Lync 2010 client settings</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ece47-165">NoPhoto</span><span class="sxs-lookup"><span data-stu-id="ece47-165">NoPhoto</span></span></p></td>
<td><p><span data-ttu-id="ece47-166">Nenhuma</span><span class="sxs-lookup"><span data-stu-id="ece47-166">none</span></span></p></td>
<td><p><span data-ttu-id="ece47-167"><strong>Não exibe minha imagem</strong></span><span class="sxs-lookup"><span data-stu-id="ece47-167"><strong>Do not show my picture</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ece47-168">PhotoFromADOnly</span><span class="sxs-lookup"><span data-stu-id="ece47-168">PhotoFromADOnly</span></span></p></td>
<td><p><span data-ttu-id="ece47-169">Active Directory</span><span class="sxs-lookup"><span data-stu-id="ece47-169">Active Directory</span></span></p></td>
<td><p><span data-ttu-id="ece47-170"><strong>Imagem empresarial padrão</strong></span><span class="sxs-lookup"><span data-stu-id="ece47-170"><strong>Default corporate picture</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ece47-171">AllPhotos</span><span class="sxs-lookup"><span data-stu-id="ece47-171">AllPhotos</span></span></p></td>
<td><p><span data-ttu-id="ece47-172">Endereço da Web</span><span class="sxs-lookup"><span data-stu-id="ece47-172">Web address</span></span></p></td>
<td><p><span data-ttu-id="ece47-173"><strong>Exibir uma imagem de um endereço Web</strong></span><span class="sxs-lookup"><span data-stu-id="ece47-173"><strong>Show a picture from a web address</strong></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="how-lync-2010-client-gets-photos"></a><span data-ttu-id="ece47-174">Como o cliente Lync 2010 recebe fotos</span><span class="sxs-lookup"><span data-stu-id="ece47-174">How Lync 2010 client gets photos</span></span>

<span data-ttu-id="ece47-175">No Lync 2010, as fotos do usuário são gerenciadas no servidor pelo serviço de catálogo de endereços.</span><span class="sxs-lookup"><span data-stu-id="ece47-175">In Lync 2010, user photos are managed on the server by the Address Book Service.</span></span> <span data-ttu-id="ece47-176">O cliente Lync Obtém as fotos do usuário consultando o serviço de consulta à Web do catálogo de endereços (ABWQ) no servidor, que é exposto por meio do serviço Web de expansão de lista de distribuição.</span><span class="sxs-lookup"><span data-stu-id="ece47-176">Lync client gets user photos by first querying the Address Book Web Query (ABWQ) service on the server, which is exposed through the Distribution List Expansion web service.</span></span> <span data-ttu-id="ece47-177">O cliente recebe o arquivo de imagem e, em seguida, copia-o para o cache do usuário para evitar o download da imagem cada vez que precisa ser exibida.</span><span class="sxs-lookup"><span data-stu-id="ece47-177">The client receives the image file and then copies it to the user's cache to avoid downloading the image each time it needs to be displayed.</span></span> <span data-ttu-id="ece47-178">Os valores de atributo retornados da consulta também são armazenados na entrada de serviço de catálogo de endereços em cache para o usuário.</span><span class="sxs-lookup"><span data-stu-id="ece47-178">The attribute values returned from the query are also stored in the cached Address Book Service entry for the user.</span></span> <span data-ttu-id="ece47-179">O serviço de catálogo de endereços exclui todas as imagens armazenadas em cache a cada 24 horas, o que significa que pode levar até 24 horas para que as novas imagens de usuário sejam atualizadas no cache do servidor.</span><span class="sxs-lookup"><span data-stu-id="ece47-179">The Address Book Service deletes all cached images every 24 hours, which means that it can take up to 24 hours for new user images to be updated in the cache on the server.</span></span> <span data-ttu-id="ece47-180">Você pode forçar uma atualização para o cache usando o cmdlet [Update-CsAddressBook](https://docs.microsoft.com/powershell/module/skype/Update-CsAddressBook) .</span><span class="sxs-lookup"><span data-stu-id="ece47-180">You can force an update to the cache by using the [Update-CsAddressBook](https://docs.microsoft.com/powershell/module/skype/Update-CsAddressBook) cmdlet.</span></span>

<span data-ttu-id="ece47-181">As fotos do usuário incluídas no status de presença também têm um valor de hash associado que o cliente Lync usa para determinar se há uma imagem mais recente disponível.</span><span class="sxs-lookup"><span data-stu-id="ece47-181">User photos included in Presence status also have an associated hash value that Lync client uses to determine whether there is a newer image available.</span></span> <span data-ttu-id="ece47-182">O cliente é notificado automaticamente sobre alterações no arquivo de imagem usado no status de presença.</span><span class="sxs-lookup"><span data-stu-id="ece47-182">The client is automatically notified of changes to the image file used in Presence status.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="ece47-183">Como as fotos não são armazenadas no banco de dados GalContacts. DB, baixar fotos do usuário não depende da configuração <STRONG>AddressBookAvailability</STRONG> na política do cliente (<A href="https://go.microsoft.com/fwlink/p/?linkid=507508">set-CsClientPolicy</A>).</span><span class="sxs-lookup"><span data-stu-id="ece47-183">Because photos are not stored in the GalContacts.db database, downloading user photos is not dependent on the <STRONG>AddressBookAvailability</STRONG> setting in the client policy (<A href="https://go.microsoft.com/fwlink/p/?linkid=507508">Set-CsClientPolicy</A>).</span></span>



</div>

<span data-ttu-id="ece47-184">A consulta para o serviço ABWQ inclui os seguintes atributos:</span><span class="sxs-lookup"><span data-stu-id="ece47-184">The query to the ABWQ service includes the following attributes:</span></span>

  - <span data-ttu-id="ece47-185">**Fotohash**     O valor de hash dos dados de foto binários e é usado para determinar se a foto atual foi alterada.</span><span class="sxs-lookup"><span data-stu-id="ece47-185">**PhotoHash**   The hash value of the binary photo data, and is used to determine whether the current photo has changed.</span></span>

  - <span data-ttu-id="ece47-186">**PhotoRelPath**     O caminho relativo para o arquivo de imagem armazenado no servidor.</span><span class="sxs-lookup"><span data-stu-id="ece47-186">**PhotoRelPath**   The relative path to the image file stored on the server.</span></span>

  - <span data-ttu-id="ece47-187">**Fotosize**     O tamanho do arquivo de imagem, em bytes.</span><span class="sxs-lookup"><span data-stu-id="ece47-187">**PhotoSize**   The size of the image file, in bytes.</span></span>

  - <span data-ttu-id="ece47-188">**Timestamp**     A data e a hora em que o arquivo de imagem foi baixado pela última vez no servidor e copiado para o cache do cliente.</span><span class="sxs-lookup"><span data-stu-id="ece47-188">**TimeStamp**   The date and time at which the image file was last downloaded from the server and copied to the client cache.</span></span>

<span data-ttu-id="ece47-189">Em seguida, após recuperar o arquivo de imagem, o cliente Lync 2010 compara os valores de atributo retornados da consulta com relação aos valores de atributo recebidos pelo cliente do provisionamento em banda para ver se eles são diferentes.</span><span class="sxs-lookup"><span data-stu-id="ece47-189">Next, after retrieving the image file, Lync 2010 client compares the attribute values returned from the query against the attribute values received by the client from in-band provisioning to see if they are different.</span></span> <span data-ttu-id="ece47-190">Se os valores forem diferentes, o cliente recupera o arquivo de imagem do usuário conectado com uma solicitação HTTP GET.</span><span class="sxs-lookup"><span data-stu-id="ece47-190">If the values are different, the client retrieves the image file of the signed-in user with an HTTP GET request.</span></span>

<span data-ttu-id="ece47-191">Além disso, o cliente verifica com o servidor a cada 24 horas a partir do momento em que a versão em cache do arquivo de imagem foi criada para comparar o valor do atributo **keyhash** no servidor com o valor no cliente.</span><span class="sxs-lookup"><span data-stu-id="ece47-191">Additionally, the client checks with the server every 24 hours from the time at which the cached version of the image file was created to compare the value of the **PhotoHash** attribute on the server with the value on the client.</span></span> <span data-ttu-id="ece47-192">Se os valores forem diferentes, o cliente saberá que o arquivo de imagem foi alterado.</span><span class="sxs-lookup"><span data-stu-id="ece47-192">If the values are different, the client knows that the image file has changed.</span></span> <span data-ttu-id="ece47-193">Para obter o arquivo de imagem atualizado, o cliente consulta novamente o serviço ABWQ para atualizar o arquivo de imagem no cache do cliente com o arquivo de imagem no servidor, que também redefine o **carimbo de data/hora** no arquivo no cache do cliente.</span><span class="sxs-lookup"><span data-stu-id="ece47-193">To obtain the updated image file, the client again queries the ABWQ service to update the image file in the client cache with the image file on the server, which also resets the **TimeStamp** on the file in the client cache.</span></span>

<span data-ttu-id="ece47-194">Veja a seguir um exemplo de resposta a uma consulta para o serviço ABWQ:</span><span class="sxs-lookup"><span data-stu-id="ece47-194">The following is an example response to a query to the ABWQ service:</span></span>
```xml
    <Attribute>
              <Name>PhotoRelPath</Name>
              <Value>efa6096aed2746cb9ab2037f7dbdde9d.f2eeeb5946db54a7aa607ecd3ae09d
              95.photo</Value>
              <Values xmlns:d6p1="http://schemas.microsoft.com/2003/10/Serialization/Arrays" i:nil="true" />
    </Attribute>
    <Attribute>
              <Name>PhotoHash</Name>
              <Value>f2eeeb5946db54a7aa607ecd3ae09d95</Value>
              <Values xmlns:d6p1="http://schemas.microsoft.com/2003/10/Serialization/Arrays" i:nil="true" />
    </Attribute>
    <Attribute>
         <Name>PhotoSize</Name>
         <Value>4620</Value>
         <Valuesxmlns:d6p1="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
    i:nil="true" />
    </Attribute>
```

</div>

</div>

<div>

## <a name="user-photos-in-lync-2013"></a><span data-ttu-id="ece47-195">Fotos do usuário no Lync 2013</span><span class="sxs-lookup"><span data-stu-id="ece47-195">User photos in Lync 2013</span></span>

<span data-ttu-id="ece47-196">O Lync 2013 introduziu suporte para imagens de alta resolução para fotos do usuário.</span><span class="sxs-lookup"><span data-stu-id="ece47-196">Lync 2013 introduced support for high-resolution images for user photos.</span></span> <span data-ttu-id="ece47-197">O Lync 2013 também inclui suporte para o armazenamento de fotos do usuário na caixa de correio do usuário no Exchange 2013, que remove a resolução da imagem e as limitações de tamanho presentes no Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="ece47-197">Lync 2013 also includes support for storing user photos in the user's mailbox on Exchange 2013, which removes the image resolution and size limitations present in Lync 2010.</span></span> <span data-ttu-id="ece47-198">As fotos do usuário no Lync 2013 podem ter até 648 pixels por 648 pixels com um tamanho de arquivo de até 20 MB.</span><span class="sxs-lookup"><span data-stu-id="ece47-198">User photos in Lync 2013 can be up to 648 pixels by 648 pixels with a file size of up to 20 MB.</span></span> <span data-ttu-id="ece47-199">As fotos de alta resolução no Lync 2013 devem estar localizadas na caixa de correio do usuário no Exchange 2013 e são suportadas apenas com o cliente Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="ece47-199">High-resolution photos in Lync 2013 must be located in the user's mailbox on Exchange 2013, and are supported only with Lync 2013 client.</span></span> <span data-ttu-id="ece47-200">Essa integração com o Exchange tira proveito da nova estrutura de autorização incluída nas versões 2013 do Lync, Exchange e SharePoint chamados OAuth.</span><span class="sxs-lookup"><span data-stu-id="ece47-200">This integration with Exchange takes advantage of the new authorization framework included in the 2013 versions of Lync, Exchange, and SharePoint called Oauth.</span></span>

<span data-ttu-id="ece47-201">Se o Exchange 2013 não for usado em sua implantação, o suporte para fotos do usuário é o mesmo que com o Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="ece47-201">If Exchange 2013 is not used in your deployment, support for user photos is the same as with Lync 2010.</span></span> <span data-ttu-id="ece47-202">No entanto, as opções de usuário para escolher a foto a ser usada são diferentes no cliente Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="ece47-202">However, the user options to choose the photo to use are different in Lync 2013 client.</span></span> <span data-ttu-id="ece47-203">No cliente Lync 2013, os usuários podem selecionar **ocultar minha imagem** ou **mostrar minha imagem**.</span><span class="sxs-lookup"><span data-stu-id="ece47-203">In Lync 2013 client, users can select either **Hide my picture** or **Show my picture**.</span></span> <span data-ttu-id="ece47-204">A opção **mostrar uma imagem de um site** não está disponível por padrão, mas pode ser habilitada por meio da atribuição de uma política de cliente.</span><span class="sxs-lookup"><span data-stu-id="ece47-204">The option **Show a picture from a website** is not available by default, but can be enabled by assigning a client policy.</span></span>

<div>

## <a name="hide-my-picture"></a><span data-ttu-id="ece47-205">Ocultar minha imagem</span><span class="sxs-lookup"><span data-stu-id="ece47-205">Hide my picture</span></span>

<span data-ttu-id="ece47-206">As configurações das fotos do usuário estão na caixa de diálogo **Opções** no Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="ece47-206">Settings for user photos are on the **Options** dialog in Lync 2013.</span></span> <span data-ttu-id="ece47-207">Quando você escolhe **ocultar minha imagem**, nenhuma foto do usuário é exibida para você no cliente do Lync, mas sua foto ainda é exibida no cartão de visita e fora do Lync.</span><span class="sxs-lookup"><span data-stu-id="ece47-207">When you choose **Hide my picture**, no user photo is displayed for you in Lync client, but your photo is still displayed on your contact card and outside of Lync.</span></span>

</div>

<div>

## <a name="show-my-picture"></a><span data-ttu-id="ece47-208">Mostrar minha imagem</span><span class="sxs-lookup"><span data-stu-id="ece47-208">Show my picture</span></span>

<span data-ttu-id="ece47-209">Quando você escolhe a opção **mostrar minha imagem** , sua foto do usuário é exibida no seu cliente do Lync e outros usuários em conversas do Lync.</span><span class="sxs-lookup"><span data-stu-id="ece47-209">When you choose the **Show my picture** option, your user photo is displayed in your Lync client and to other users in Lync conversations.</span></span> <span data-ttu-id="ece47-210">A imagem usada é aquela armazenada no AD DS.</span><span class="sxs-lookup"><span data-stu-id="ece47-210">The image used is the one stored in AD DS.</span></span>

</div>

<div>

## <a name="show-a-picture-from-a-website"></a><span data-ttu-id="ece47-211">Mostrar uma imagem de um site</span><span class="sxs-lookup"><span data-stu-id="ece47-211">Show a picture from a website</span></span>

<span data-ttu-id="ece47-212">A opção **Mostrar imagem de um site** fica disponível no Lync 2013 depois que uma política de cliente é configurada para habilitá-la.</span><span class="sxs-lookup"><span data-stu-id="ece47-212">The **Show picture from a website** option becomes available in Lync 2013 after a client policy is set to enable it.</span></span> <span data-ttu-id="ece47-213">A versão do cliente deve ser mais recente do que o 15.0.4535.1002, que é instalado com as [atualizações cumulativas do Lync: novembro de 2013](https://go.microsoft.com/fwlink/p/?linkid=509908).</span><span class="sxs-lookup"><span data-stu-id="ece47-213">The client version must be newer than 15.0.4535.1002, which is installed with the [Lync Cumulative Updates: November 2013](https://go.microsoft.com/fwlink/p/?linkid=509908).</span></span> <span data-ttu-id="ece47-214">Talvez os usuários precisem fazer logout e voltar novamente para ver as alterações no cliente.</span><span class="sxs-lookup"><span data-stu-id="ece47-214">Users may need to log out and then back in again to see the changes in the client.</span></span>

<span data-ttu-id="ece47-215">Você pode definir a política de cliente para permitir que **mostre a imagem de uma configuração de site** executando a política [set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) no Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ece47-215">You can set the client policy to enable to **Show picture from a website** setting by running the [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) policy in the Lync Server Management Shell.</span></span> <span data-ttu-id="ece47-216">Os cmdlets de exemplo a seguir demonstram como definir a política globalmente para todos os usuários em sua implantação:</span><span class="sxs-lookup"><span data-stu-id="ece47-216">The following example cmdlets demonstrate how to set the policy globally for all users in your deployment:</span></span>

   ```powershell
    $pe=New-CsClientPolicyEntry -Name EnablePresencePhotoOptions -Value True
   ```

   ```powershell
    $po=Get-CsClientPolicy -Identity Global
   ```

   ```powershell
    $po.PolicyEntry.Add($pe)
   ```

   ```powershell
    Set-CsClientPolicy -Instance $po
   ```


<span data-ttu-id="ece47-217">Quando uma imagem é carregada para a caixa de correio do usuário, o Exchange cria automaticamente uma versão de resolução inferior da imagem que pode ser usada em aplicativos cliente.</span><span class="sxs-lookup"><span data-stu-id="ece47-217">When an image is uploaded to the user’s mailbox, Exchange automatically creates a lower resolution version of the image which can be used in client applications.</span></span> <span data-ttu-id="ece47-218">A foto do usuário também é atualizada no AD DS.</span><span class="sxs-lookup"><span data-stu-id="ece47-218">The user photo is also updated in AD DS.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="ece47-219">Quando um arquivo de imagem é atualizado no AD DS, uma imagem de 48 x 48 pixel é criada e usada para o thumbnailPhoto no AD DS.</span><span class="sxs-lookup"><span data-stu-id="ece47-219">When an image file is updated in AD DS, a 48 x 48 pixel image is created and used for the thumbnailPhoto in AD DS.</span></span> <span data-ttu-id="ece47-220">Qualquer imagem existente será substituída.</span><span class="sxs-lookup"><span data-stu-id="ece47-220">Any existing image is replaced.</span></span> <span data-ttu-id="ece47-221">Portanto, se você tiver adicionado uma imagem 96 x 96 ao AD DS, ela será substituída pela nova imagem de 48 x 48.</span><span class="sxs-lookup"><span data-stu-id="ece47-221">So if you added a 96 x 96 image to AD DS, it will be overwritten with the new 48 x 48 image.</span></span> <span data-ttu-id="ece47-222">Isso só é importante se você tiver usuários em seu ambiente usando os clientes do Lync 2010, pois esses clientes obterão fotos do usuário do AD DS.</span><span class="sxs-lookup"><span data-stu-id="ece47-222">This is only important is you have users in your environment using Lync 2010 clients, as those clients will obtain user photos from AD DS.</span></span> <span data-ttu-id="ece47-223">Você pode importar imagens de 96 x 96 pixels para substituir as criadas pelo AD DS se tiver clientes do Lync 2010 em sua organização.</span><span class="sxs-lookup"><span data-stu-id="ece47-223">You can import 96 x 96 pixel images to replace the ones created by AD DS if you have Lync 2010 clients in your organization.</span></span>



</div>

</div>

<div>

## <a name="user-photo-support-in-lync-2013"></a><span data-ttu-id="ece47-224">Suporte de foto do usuário no Lync 2013</span><span class="sxs-lookup"><span data-stu-id="ece47-224">User photo support in Lync 2013</span></span>

<span data-ttu-id="ece47-225">No Lync 2013, são suportadas três resoluções de imagem para as fotos do usuário, conforme descrito na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="ece47-225">In Lync 2013, three image resolutions are supported for user photos as described in the following table.</span></span> <span data-ttu-id="ece47-226">A imagem usada é determinada pela configuração de política de cliente atribuída aos usuários do Lync.</span><span class="sxs-lookup"><span data-stu-id="ece47-226">The image that is used is determined by the client policy setting assigned to Lync users.</span></span> <span data-ttu-id="ece47-227">Consulte "Gerenciando fotos do usuário com cmdlets de política de cliente" neste tópico para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="ece47-227">See “Managing user’s photo with Client Policy cmdlets” in this topic for more information.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ece47-228">Resolução de imagem (pixels)</span><span class="sxs-lookup"><span data-stu-id="ece47-228">Image resolution (pixels)</span></span></th>
<th><span data-ttu-id="ece47-229">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="ece47-229">Application</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ece47-230">48 x 48</span><span class="sxs-lookup"><span data-stu-id="ece47-230">48 x 48</span></span></p></td>
<td><p><span data-ttu-id="ece47-231">Usado se nenhuma imagem de resolução superior estiver selecionada</span><span class="sxs-lookup"><span data-stu-id="ece47-231">Used if no higher resolution image is selected</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ece47-232">96 x 96</span><span class="sxs-lookup"><span data-stu-id="ece47-232">96 x 96</span></span></p></td>
<td><p><span data-ttu-id="ece47-233">Usado no Outlook Web App e no Outlook 2013</span><span class="sxs-lookup"><span data-stu-id="ece47-233">Used in Outlook Web App and Outlook 2013</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ece47-234">648 x 648</span><span class="sxs-lookup"><span data-stu-id="ece47-234">648 x 648</span></span></p></td>
<td><p><span data-ttu-id="ece47-235">Usado no cliente de área de trabalho Lync 2013 e Lync 2013 Web App</span><span class="sxs-lookup"><span data-stu-id="ece47-235">Used in Lync 2013 desktop client and Lync 2013 Web App</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ece47-236">Qualquer usuário com uma caixa de correio habilitada no Exchange 2013 pode carregar uma imagem diferente, incluindo fotos de alta resolução, através do Outlook Web Access ou do Lync 2013 Client Options.</span><span class="sxs-lookup"><span data-stu-id="ece47-236">Any user with a mailbox enabled in Exchange 2013 can upload a different image, including high-resolution photos, through Outlook Web Access or Lync 2013 client options.</span></span> <span data-ttu-id="ece47-237">As configurações recomendadas para imagens usadas incluem:</span><span class="sxs-lookup"><span data-stu-id="ece47-237">The recommended settings for images used include:</span></span>

  - <span data-ttu-id="ece47-238">**Resolução**     de imagem 648 por 648 pixels</span><span class="sxs-lookup"><span data-stu-id="ece47-238">**Image Resolution**   648 by 648 pixels</span></span>

  - <span data-ttu-id="ece47-239">**Intensidade**     de cor 24 bits</span><span class="sxs-lookup"><span data-stu-id="ece47-239">**Color Depth**   24-bit</span></span>

  - <span data-ttu-id="ece47-240">Tamanho do arquivo de **imagem**     até 20 MB</span><span class="sxs-lookup"><span data-stu-id="ece47-240">**Image file size**   up to 20 MB</span></span>

  - <span data-ttu-id="ece47-241">**Formato**     de arquivo FORMATO</span><span class="sxs-lookup"><span data-stu-id="ece47-241">**File format**   JPEG</span></span>

<span data-ttu-id="ece47-242">Uma imagem JPEG de 24 bits típica de 648 pixels por 648 pixels tem um tamanho de arquivo de aproximadamente 240 KB, portanto, 1 MB de espaço de armazenamento é necessário para cada 4 fotos do usuário.</span><span class="sxs-lookup"><span data-stu-id="ece47-242">A typical 24-bit JPEG image that is 648 pixels by 648 pixels has a file size of about 240 KB, so 1 MB of storage space is needed for every 4 user photos.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

