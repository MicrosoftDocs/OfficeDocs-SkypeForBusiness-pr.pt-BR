---
title: Como as fotos do usuário são exibidas no Lync
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: How user photos are displayed in Lync
ms:assetid: b44a364d-a1d2-4d45-b27a-b5f77775e233
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn783119(v=OCS.15)
ms:contentKeyID: 62835297
ms.date: 08/27/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ac13f066c24f66640aee1360caf1d341d604474
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40971167"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="how-user-photos-are-displayed-in-lync"></a><span data-ttu-id="e3fa7-102">Como as fotos do usuário são exibidas no Lync</span><span class="sxs-lookup"><span data-stu-id="e3fa7-102">How user photos are displayed in Lync</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e3fa7-103">_**Tópico da última modificação:** 2014-08-25_</span><span class="sxs-lookup"><span data-stu-id="e3fa7-103">_**Topic Last Modified:** 2014-08-25_</span></span>

<span data-ttu-id="e3fa7-104">**Resumo:** As fotos do usuário exibidas no Lync Client podem ser diferentes dependendo de qual recurso do Lync você está usando, como quando está em uma conferência ou um chat de mensagem instantânea.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-104">**Summary:** User photos displayed in Lync client can be different depending on which Lync feature you are using, such as when in a conference or an IM chat.</span></span>

<span data-ttu-id="e3fa7-105">O Lync 2010 introduziu a capacidade de incluir uma foto com o seu perfil do Lync que é exibido para outros usuários do Lync.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-105">Lync 2010 introduced the ability to include a photo with your Lync profile that is displayed to other Lync users.</span></span> <span data-ttu-id="e3fa7-106">Você também pode escolher se deseja ou não exibir fotos para seus contatos no cliente do Lync.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-106">You can also choose whether or not to display photos for your contacts in Lync client.</span></span> <span data-ttu-id="e3fa7-107">No Lync 2013, suporte para fotos de alta resolução para usuários.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-107">In Lync 2013, support for high-resolution photos for users.</span></span> <span data-ttu-id="e3fa7-108">Este tópico descreve como o Lync Client Obtém e exibe as fotos do usuário, onde as imagens são armazenadas, as limitações para cada fonte de imagem e como as fotos do usuário são usadas por diferentes serviços do Lync.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-108">This topic describes how Lync client gets and displays user photos, where the images are stored, the limitations for each image source, and how user photos are used by different Lync services.</span></span>

<div>

## <a name="planning-considerations"></a><span data-ttu-id="e3fa7-109">Considerações de planejamento</span><span class="sxs-lookup"><span data-stu-id="e3fa7-109">Planning considerations</span></span>

<span data-ttu-id="e3fa7-110">Você deve considerar o seguinte ao planejar a implementação do suporte para fotos de usuários.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-110">You should consider the following when planning to implement support for user photos.</span></span>

  - <span data-ttu-id="e3fa7-111">O suporte para foto de usuário de alta definição requer que a caixa de correio do usuário esteja localizada no Exchange 2013 e a conta de usuário do Lync esteja no pool do Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-111">High-definition user photo support requires that the user’s mailbox be located on Exchange 2013 and the Lync user account to be in Lync 2013 pool.</span></span>

  - <span data-ttu-id="e3fa7-112">Só há suporte para fotos de usuários de alta definição em um ambiente no qual o Lync Server 2013 e o Exchange 2013 são usados.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-112">High-definition user photos are supported only in an environment where both Lync Server 2013 and Exchange 2013 are used.</span></span>

  - <span data-ttu-id="e3fa7-113">Os usuários com caixas de correio no Exchange 2010 sempre usarão o atributo **ThumbNailPhoto** do AD DS como a origem da foto do usuário.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-113">Users with Mailboxes on Exchange 2010 will always use the **thumbnailPhoto** attribute from AD DS as the source for their user photo.</span></span>

  - <span data-ttu-id="e3fa7-114">Uma foto do usuário armazenada como o atributo **ThumbNailPhoto** do AD DS não será exibida para contatos externos/federados.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-114">A user photo stored as the **thumbnailPhoto** attribute from AD DS will not be displayed to external / federated contacts.</span></span>

  - <span data-ttu-id="e3fa7-115">Se as fotos dos contatos do usuário estiverem armazenadas no AD DS, o arquivo de imagem usado será limitado a 96 × 96 pixels e não mais do que 100 KB de tamanho de arquivo.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-115">If the photos for user contacts are stored in AD DS, the image file used is limited to 96×96 pixels and no more than 100 KB file size.</span></span>

  - <span data-ttu-id="e3fa7-116">Se a conectividade entre o Lync Server e o Exchange Server for perdida, o **ThumbNailPhoto** de baixa resolução do usuário do AD DS será exibido e somente para usuários internos.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-116">If connectivity between Lync Server and Exchange Server is lost, the user’s low resolution **thumbnailPhoto** from AD DS will be displayed, and to internal users only.</span></span>

  - <span data-ttu-id="e3fa7-117">Fotos de usuário de alta resolução são exibidas em reuniões do Lync 2013 quando um alto-falante ativo não está habilitado para vídeo.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-117">High-resolution user photos are displayed in Lync 2013 meetings when an active speaker does not have video enabled.</span></span> <span data-ttu-id="e3fa7-118">Além disso, mover o mouse sobre a foto em miniatura na Galeria mostrará a foto de alta resolução.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-118">Also, moving the mouse over thumbnail photo in the gallery will display the high-resolution photo.</span></span>

</div>

<div>

## <a name="user-photos-in-lync-2010"></a><span data-ttu-id="e3fa7-119">Fotos do usuário no Lync 2010</span><span class="sxs-lookup"><span data-stu-id="e3fa7-119">User Photos in Lync 2010</span></span>

<span data-ttu-id="e3fa7-120">No cliente do Lync 2010, você pode escolher entre duas opções para exibir uma foto do seu perfil, a **imagem corporativa padrão** e **mostrar uma imagem de um endereço Web**.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-120">In the Lync 2010 client, you can choose from two options to display a photo for your profile, **Default corporate picture** and **Show picture from a web address**.</span></span>

<div>

## <a name="default-corporate-picture"></a><span data-ttu-id="e3fa7-121">Imagem empresarial padrão</span><span class="sxs-lookup"><span data-stu-id="e3fa7-121">Default corporate picture</span></span>

<span data-ttu-id="e3fa7-122">Quando você escolhe a opção **padrão de imagem corporativa** , o Lync Obtém a foto exibida para você nos serviços de domínio do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-122">When you choose the **Default corporate picture** option, Lync gets the photo displayed for you from Active Directory Domain Services.</span></span> <span data-ttu-id="e3fa7-123">A imagem usada é a imagem definida como o valor do atributo **ThumbNailPhoto** nos serviços de domínio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-123">The image used is the image defined as the value for the **thumbnailPhoto** attribute in Active Directory Domain Services.</span></span> <span data-ttu-id="e3fa7-124">Esse é o mesmo arquivo usado pelo Exchange para exibir imagens no Outlook.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-124">This is the same file that is used by Exchange to display images in Outlook.</span></span>

<span data-ttu-id="e3fa7-125">As considerações sobre o uso de imagens dos serviços de domínio Active Directory incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e3fa7-125">Considerations for using images from Active Directory Domain Services include the following:</span></span>

  - <span data-ttu-id="e3fa7-126">Só há suporte para imagens com dimensões de até 96 pixels por 96 pixels.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-126">Only images with dimensions up to 96 pixels by 96 pixels are supported.</span></span> <span data-ttu-id="e3fa7-127">O tamanho do arquivo da imagem é limitado a 100 KB.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-127">The file size for the image is limited to 100 KB.</span></span>

  - <span data-ttu-id="e3fa7-128">Por padrão, os usuários podem alterar a imagem usada para o atributo **ThumbNailPhoto** , mas não diretamente pelo cliente do Lync.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-128">By default, users are able to change the image used for the **thumbnailPhoto** attribute, though not directly through Lync client.</span></span> <span data-ttu-id="e3fa7-129">Você pode desabilitá-lo por meio dos serviços de domínio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-129">You can disable this through Active Directory Domain Services.</span></span>

  - <span data-ttu-id="e3fa7-130">As imagens armazenadas nos serviços de domínio Active Directory não são exibidas para contatos externos à sua organização, mesmo que sejam contatos federados.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-130">Images stored in Active Directory Domain Services are not displayed to contacts external to your organization, even if they are federated contacts.</span></span>

  - <span data-ttu-id="e3fa7-131">Em grandes organizações, armazenar e recuperar as imagens para um grande número de usuários pode afetar o tamanho e o desempenho do banco de dados dos serviços de domínio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-131">In large organizations, storing and retrieving the images for large numbers of users may impact the Active Directory Domain Services database size and performance.</span></span>

  - <span data-ttu-id="e3fa7-132">As dimensões de imagem limitada e o tamanho do arquivo significam que apenas imagens de baixa resolução podem ser usadas.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-132">The limited image dimensions and file size mean that only low resolution images can be used.</span></span>

<div>

## <a name="how-users-manage-their-user-photos-in-active-directory-domain-services"></a><span data-ttu-id="e3fa7-133">Como os usuários gerenciam suas fotos de usuários nos serviços de domínio do Active Directory</span><span class="sxs-lookup"><span data-stu-id="e3fa7-133">How users manage their user photos in Active Directory Domain Services</span></span>

<span data-ttu-id="e3fa7-134">O usuário não pode alterar a imagem usada no perfil dos serviços de domínio Active Directory diretamente pelo cliente do Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-134">User cannot change the image used in their Active Directory Domain Services profile directly through Lync 2010 client.</span></span> <span data-ttu-id="e3fa7-135">Elas podem usar uma das seguintes opções para fazer isso, se disponíveis:</span><span class="sxs-lookup"><span data-stu-id="e3fa7-135">They can use one of the following options to do so, if available:</span></span>

  - <span data-ttu-id="e3fa7-136">**Os usuários do SharePoint Server**   podem carregar uma foto em "meu site" em um servidor do SharePoint e, em seguida, [Configurar a sincronização do perfil no SharePoint](http://go.microsoft.com/fwlink/p/?linkid=507466) para sincronizar a foto com o atributo **ThumbNailPhoto** nos serviços de domínio do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-136">**SharePoint Server**   Users can upload a photo to ‘My Site’ on a SharePoint Server and then [configure profile synchronization in SharePoint](http://go.microsoft.com/fwlink/p/?linkid=507466) to synchronize the photo to the **thumbnailPhoto** attribute in Active Directory Domain Services.</span></span>

  - <span data-ttu-id="e3fa7-137">**Foto armazenada em URL**   publicamente acessível os usuários podem configurar a foto do usuário especificando uma URL publicamente acessível para a imagem que desejam usar.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-137">**Photo stored on publicly accessible URL**   Users can configure their user photo specifying a publicly accessible URL for the image that they want to use.</span></span> <span data-ttu-id="e3fa7-138">A imagem deve ser acessível publicamente sem uma senha.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-138">The image must be publicly accessible without a password.</span></span> <span data-ttu-id="e3fa7-139">A imagem armazenada no endereço Web especificado é transferida para outros usuários por meio da categoria de cartão de visita nas informações de presença.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-139">The image stored at the specified web address is transferred to other users through the contact card category in the presence information.</span></span> <span data-ttu-id="e3fa7-140">Quando o cliente do Lync precisa exibir uma foto do usuário, ele recupera a imagem do endereço Web especificado.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-140">When Lync client needs to display a user photo, it retrieves the image from the specified web address.</span></span>

  - <span data-ttu-id="e3fa7-141">**Cmdlets do Exchange 2010 para administradores do Windows PowerShell**   podem executar o cmdlet [Import-RecipientDataProperty](http://go.microsoft.com/fwlink/p/?linkid=507468) no Shell de gerenciamento do Exchange 2010 para gerenciar o atributo **ThumbNailPhoto** .</span><span class="sxs-lookup"><span data-stu-id="e3fa7-141">**Exchange 2010 cmdlets for Windows PowerShell**   Administrators can run the [Import-RecipientDataProperty](http://go.microsoft.com/fwlink/p/?linkid=507468) cmdlet in the Exchange 2010 Management Shell in to manage the **thumbnailPhoto** attribute.</span></span> <span data-ttu-id="e3fa7-142">Quando as imagens são importadas com cmdlets do Exchange 2010, o tamanho do arquivo limita-se a 10 KB.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-142">When images are imported with Exchange 2010 cmdlets, the file size is limited to 10 KB.</span></span>

  - <span data-ttu-id="e3fa7-143">**Ferramentas de terceiros**   os usuários podem carregar apenas suas próprias fotos para o atributo **ThumbNailPhoto** .</span><span class="sxs-lookup"><span data-stu-id="e3fa7-143">**Third Party tools**   Users can upload only their own photo to for the **thumbnailPhoto** attribute.</span></span>

</div>

</div>

<div>

## <a name="show-a-picture-from-a-web-address"></a><span data-ttu-id="e3fa7-144">Mostrar uma imagem de um endereço Web</span><span class="sxs-lookup"><span data-stu-id="e3fa7-144">Show a picture from a web address</span></span>

<span data-ttu-id="e3fa7-145">Quando você escolhe a opção **mostrar uma imagem de um endereço Web** , o Lync Obtém a imagem no endereço que você inserir e a exibe para a foto do usuário no Lync.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-145">When you choose the **Show a picture from a web address** option, Lync gets the image at the address you enter and displays it for your user photo in Lync.</span></span>

<span data-ttu-id="e3fa7-146">As considerações para usar imagens de um endereço da Web incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e3fa7-146">Considerations for using images from a web address include the following:</span></span>

  - <span data-ttu-id="e3fa7-147">Os limites de tamanho de arquivo são determinados pelo atributo **MaxPhotoSizeKB** na política do cliente, definido com o cmdlet [New-CsClientPolicy](http://go.microsoft.com/fwlink/p/?linkid=507463) .</span><span class="sxs-lookup"><span data-stu-id="e3fa7-147">File size limits are determined by the **MaxPhotoSizeKB** attribute in the client policy, defined with the [New-CsClientPolicy](http://go.microsoft.com/fwlink/p/?linkid=507463) cmdlet.</span></span> <span data-ttu-id="e3fa7-148">O limite de tamanho padrão é 30 KB.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-148">The default size limit is 30 KB.</span></span> <span data-ttu-id="e3fa7-149">O valor máximo é 100 KB.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-149">The maximum value is 100 KB.</span></span> <span data-ttu-id="e3fa7-150">Não há restrição na resolução da imagem, mas se você tentar usar um arquivo de imagem que excede o limite de tamanho, ele não será baixado para os clientes do Lync.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-150">There is no restriction on the resolution of the image, but if you try to use an image file that exceeds the size limit it will not be downloaded to Lync clients.</span></span> <span data-ttu-id="e3fa7-151">Você pode definir o valor como 0 para desativar a utilização de todas as fotos do usuário no Lync.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-151">You can set the value to 0 to disable all user photos from being used in Lync.</span></span>

  - <span data-ttu-id="e3fa7-152">As fotos do usuário de um endereço da Web podem ser vistas por contatos federados externos.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-152">User photos from a web address can be seen by external federated contacts.</span></span>

</div>

<div>

## <a name="managing-users-photo-with-client-policy-cmdlets"></a><span data-ttu-id="e3fa7-153">Gerenciando fotos do usuário com cmdlets da política do cliente</span><span class="sxs-lookup"><span data-stu-id="e3fa7-153">Managing user’s photo with Client Policy cmdlets</span></span>

<span data-ttu-id="e3fa7-154">No Lync Server 2010, as configurações de política do cliente são configuradas com os cmdlets CsClientPolicy.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-154">In Lync Server 2010, client policy settings are configured with the CsClientPolicy cmdlets.</span></span> <span data-ttu-id="e3fa7-155">As configurações de política definidas são enviadas aos clientes por meio do provisionamento em banda.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-155">The configured policy settings are sent to clients through in-band provisioning.</span></span> <span data-ttu-id="e3fa7-156">Os dois parâmetros dos cmdlets CsClientPolicy que determinam a experiência de foto do usuário são **DisplayPhoto** e **MaxPhotoSizeKB**.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-156">The two parameters of the CsClientPolicy cmdlets that determine the user photo experience are **DisplayPhoto** and **MaxPhotoSizeKB**.</span></span> <span data-ttu-id="e3fa7-157">O parâmetro de provisionamento em banda correspondente para **DisplayPhoto** e **MaxPhotoSizeKB** é chamado de **superutilização**.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-157">The corresponding in-band provisioning parameter for **DisplayPhoto** and **MaxPhotoSizeKB** is named **PhotoUsage**.</span></span> <span data-ttu-id="e3fa7-158">Os valores para o parâmetro **superusage** são enviados aos clientes por meio do **endpointConfiguration** **Provision**.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-158">Values for the **PhotoUsage** parameter are send to clients through the **endpointConfiguration** **provisionGroup**.</span></span> <span data-ttu-id="e3fa7-159">Consulte [visão geral das políticas e configurações do cliente](http://go.microsoft.com/fwlink/?linkid=507470) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-159">See [Overview of Client Policies and Settings](http://go.microsoft.com/fwlink/?linkid=507470) for more information.</span></span>

<span data-ttu-id="e3fa7-160">O valor do parâmetro **DisplayPhoto** determina a origem da imagem de foto do usuário.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-160">The **DisplayPhoto** parameter value determines the source of the user's photo image.</span></span> <span data-ttu-id="e3fa7-161">Os valores com suporte estão incluídos na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-161">The supported values are included in the following table.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e3fa7-162">Valor do parâmetro DisplayPhoto</span><span class="sxs-lookup"><span data-stu-id="e3fa7-162">DisplayPhoto parameter value</span></span></th>
<th><span data-ttu-id="e3fa7-163">Fonte de imagem</span><span class="sxs-lookup"><span data-stu-id="e3fa7-163">Image source</span></span></th>
<th><span data-ttu-id="e3fa7-164">Configurações do cliente do Lync 2010</span><span class="sxs-lookup"><span data-stu-id="e3fa7-164">Lync 2010 client settings</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e3fa7-165">Não fotográfico</span><span class="sxs-lookup"><span data-stu-id="e3fa7-165">NoPhoto</span></span></p></td>
<td><p><span data-ttu-id="e3fa7-166">nenhuma</span><span class="sxs-lookup"><span data-stu-id="e3fa7-166">none</span></span></p></td>
<td><p><span data-ttu-id="e3fa7-167"><strong>Não mostrar minha imagem</strong></span><span class="sxs-lookup"><span data-stu-id="e3fa7-167"><strong>Do not show my picture</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3fa7-168">PhotoFromADOnly</span><span class="sxs-lookup"><span data-stu-id="e3fa7-168">PhotoFromADOnly</span></span></p></td>
<td><p><span data-ttu-id="e3fa7-169">Active Directory</span><span class="sxs-lookup"><span data-stu-id="e3fa7-169">Active Directory</span></span></p></td>
<td><p><span data-ttu-id="e3fa7-170"><strong>Imagem empresarial padrão</strong></span><span class="sxs-lookup"><span data-stu-id="e3fa7-170"><strong>Default corporate picture</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3fa7-171">Fotos</span><span class="sxs-lookup"><span data-stu-id="e3fa7-171">AllPhotos</span></span></p></td>
<td><p><span data-ttu-id="e3fa7-172">Endereço Web</span><span class="sxs-lookup"><span data-stu-id="e3fa7-172">Web address</span></span></p></td>
<td><p><span data-ttu-id="e3fa7-173"><strong>Mostrar uma imagem de um endereço Web</strong></span><span class="sxs-lookup"><span data-stu-id="e3fa7-173"><strong>Show a picture from a web address</strong></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="how-lync-2010-client-gets-photos"></a><span data-ttu-id="e3fa7-174">Como o cliente do Lync 2010 Obtém fotos</span><span class="sxs-lookup"><span data-stu-id="e3fa7-174">How Lync 2010 client gets photos</span></span>

<span data-ttu-id="e3fa7-175">No Lync 2010, as fotos do usuário são gerenciadas no servidor pelo serviço de catálogo de endereços.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-175">In Lync 2010, user photos are managed on the server by the Address Book Service.</span></span> <span data-ttu-id="e3fa7-176">O Lync Client Obtém as fotos do usuário consultando o serviço de consulta à Web do catálogo de endereços (ABWQ) no servidor, que é exposto por meio do serviço Web de expansão de lista de distribuição.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-176">Lync client gets user photos by first querying the Address Book Web Query (ABWQ) service on the server, which is exposed through the Distribution List Expansion web service.</span></span> <span data-ttu-id="e3fa7-177">O cliente recebe o arquivo de imagem e, em seguida, copia-o para o cache do usuário para evitar o download da imagem toda vez que precisar ser exibido.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-177">The client receives the image file and then copies it to the user's cache to avoid downloading the image each time it needs to be displayed.</span></span> <span data-ttu-id="e3fa7-178">Os valores de atributo retornados da consulta também são armazenados na entrada de serviço de catálogo de endereços em cache para o usuário.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-178">The attribute values returned from the query are also stored in the cached Address Book Service entry for the user.</span></span> <span data-ttu-id="e3fa7-179">O serviço de catálogo de endereços exclui todas as imagens armazenadas em cache a cada 24 horas, o que significa que pode levar até 24 horas para que as novas imagens do usuário sejam atualizadas no cache do servidor.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-179">The Address Book Service deletes all cached images every 24 hours, which means that it can take up to 24 hours for new user images to be updated in the cache on the server.</span></span> <span data-ttu-id="e3fa7-180">Você pode forçar uma atualização para o cache usando o cmdlet [Update-CsAddressBook](https://docs.microsoft.com/powershell/module/skype/Update-CsAddressBook) .</span><span class="sxs-lookup"><span data-stu-id="e3fa7-180">You can force an update to the cache by using the [Update-CsAddressBook](https://docs.microsoft.com/powershell/module/skype/Update-CsAddressBook) cmdlet.</span></span>

<span data-ttu-id="e3fa7-181">As fotos do usuário incluídas no status de presença também têm um valor de hash associado que o cliente Lync usa para determinar se há uma imagem mais recente disponível.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-181">User photos included in Presence status also have an associated hash value that Lync client uses to determine whether there is a newer image available.</span></span> <span data-ttu-id="e3fa7-182">O cliente é notificado automaticamente sobre alterações no arquivo de imagem usado em status de presença.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-182">The client is automatically notified of changes to the image file used in Presence status.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="e3fa7-183">Como as fotos não são armazenadas no banco de dados GalContacts. DB, baixar fotos do usuário não depende da configuração <STRONG>AddressBookAvailability</STRONG> na política do cliente (<A href="http://go.microsoft.com/fwlink/p/?linkid=507508">set-CsClientPolicy</A>).</span><span class="sxs-lookup"><span data-stu-id="e3fa7-183">Because photos are not stored in the GalContacts.db database, downloading user photos is not dependent on the <STRONG>AddressBookAvailability</STRONG> setting in the client policy (<A href="http://go.microsoft.com/fwlink/p/?linkid=507508">Set-CsClientPolicy</A>).</span></span>



</div>

<span data-ttu-id="e3fa7-184">A consulta para o serviço ABWQ inclui os seguintes atributos:</span><span class="sxs-lookup"><span data-stu-id="e3fa7-184">The query to the ABWQ service includes the following attributes:</span></span>

  - <span data-ttu-id="e3fa7-185">**Keyhash**   o valor de hash dos dados binários da foto e é usado para determinar se a foto atual foi alterada.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-185">**PhotoHash**   The hash value of the binary photo data, and is used to determine whether the current photo has changed.</span></span>

  - <span data-ttu-id="e3fa7-186">**PhotoRelPath**   o caminho relativo para o arquivo de imagem armazenado no servidor.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-186">**PhotoRelPath**   The relative path to the image file stored on the server.</span></span>

  - <span data-ttu-id="e3fa7-187">**Fotodimensionamento**   do tamanho do arquivo de imagem em bytes.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-187">**PhotoSize**   The size of the image file, in bytes.</span></span>

  - <span data-ttu-id="e3fa7-188">**Timestamp**   a data e a hora em que o arquivo de imagem foi baixado pela última vez do servidor e copiado para o cache do cliente.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-188">**TimeStamp**   The date and time at which the image file was last downloaded from the server and copied to the client cache.</span></span>

<span data-ttu-id="e3fa7-189">Em seguida, depois de recuperar o arquivo de imagem, o cliente do Lync 2010 compara os valores de atributo retornados da consulta com os valores de atributo recebidos pelo cliente de provisionamento em banda para ver se eles são diferentes.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-189">Next, after retrieving the image file, Lync 2010 client compares the attribute values returned from the query against the attribute values received by the client from in-band provisioning to see if they are different.</span></span> <span data-ttu-id="e3fa7-190">Se os valores forem diferentes, o cliente recuperará o arquivo de imagem do usuário conectado com uma solicitação HTTP GET.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-190">If the values are different, the client retrieves the image file of the signed-in user with an HTTP GET request.</span></span>

<span data-ttu-id="e3fa7-191">Além disso, o cliente verifica com o servidor a cada 24 horas a partir do momento em que a versão em cache do arquivo de imagem foi criada para comparar o valor do atributo **cohash** no servidor com o valor no cliente.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-191">Additionally, the client checks with the server every 24 hours from the time at which the cached version of the image file was created to compare the value of the **PhotoHash** attribute on the server with the value on the client.</span></span> <span data-ttu-id="e3fa7-192">Se os valores forem diferentes, o cliente saberá que o arquivo de imagem foi alterado.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-192">If the values are different, the client knows that the image file has changed.</span></span> <span data-ttu-id="e3fa7-193">Para obter o arquivo de imagem atualizado, o cliente consulta novamente o serviço ABWQ para atualizar o arquivo de imagem no cache do cliente com o arquivo de imagem no servidor, que também redefine o **carimbo de data/hora** no arquivo no cache do cliente.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-193">To obtain the updated image file, the client again queries the ABWQ service to update the image file in the client cache with the image file on the server, which also resets the **TimeStamp** on the file in the client cache.</span></span>

<span data-ttu-id="e3fa7-194">Veja a seguir um exemplo de resposta a uma consulta para o serviço ABWQ:</span><span class="sxs-lookup"><span data-stu-id="e3fa7-194">The following is an example response to a query to the ABWQ service:</span></span>
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

## <a name="user-photos-in-lync-2013"></a><span data-ttu-id="e3fa7-195">Fotos do usuário no Lync 2013</span><span class="sxs-lookup"><span data-stu-id="e3fa7-195">User photos in Lync 2013</span></span>

<span data-ttu-id="e3fa7-196">O Lync 2013 introduziu suporte para imagens de alta resolução para fotos do usuário.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-196">Lync 2013 introduced support for high-resolution images for user photos.</span></span> <span data-ttu-id="e3fa7-197">O Lync 2013 também inclui suporte para armazenar fotos do usuário na caixa de correio do usuário no Exchange 2013, que remove a resolução da imagem e as limitações de tamanho presentes no Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-197">Lync 2013 also includes support for storing user photos in the user's mailbox on Exchange 2013, which removes the image resolution and size limitations present in Lync 2010.</span></span> <span data-ttu-id="e3fa7-198">As fotos do usuário no Lync 2013 podem ter até 648 pixels por 648 pixels com um tamanho de arquivo de até 20 MB.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-198">User photos in Lync 2013 can be up to 648 pixels by 648 pixels with a file size of up to 20 MB.</span></span> <span data-ttu-id="e3fa7-199">Fotos de alta resolução no Lync 2013 devem estar localizadas na caixa de correio do usuário no Exchange 2013 e têm suporte apenas com o cliente Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-199">High-resolution photos in Lync 2013 must be located in the user's mailbox on Exchange 2013, and are supported only with Lync 2013 client.</span></span> <span data-ttu-id="e3fa7-200">Essa integração com o Exchange aproveita a nova estrutura de autorização incluída nas versões do 2013 do Lync, Exchange e SharePoint chamados OAuth.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-200">This integration with Exchange takes advantage of the new authorization framework included in the 2013 versions of Lync, Exchange, and SharePoint called Oauth.</span></span>

<span data-ttu-id="e3fa7-201">Se o Exchange 2013 não for usado na sua implantação, o suporte para fotos do usuário é o mesmo que o Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-201">If Exchange 2013 is not used in your deployment, support for user photos is the same as with Lync 2010.</span></span> <span data-ttu-id="e3fa7-202">No entanto, as opções do usuário para escolher a foto a ser usada são diferentes no cliente do Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-202">However, the user options to choose the photo to use are different in Lync 2013 client.</span></span> <span data-ttu-id="e3fa7-203">No cliente do Lync 2013, os usuários podem selecionar **ocultar minha imagem** ou **mostrar minha imagem**.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-203">In Lync 2013 client, users can select either **Hide my picture** or **Show my picture**.</span></span> <span data-ttu-id="e3fa7-204">A opção **mostrar uma imagem de um site** não está disponível por padrão, mas pode ser habilitada ao atribuir uma política de cliente.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-204">The option **Show a picture from a website** is not available by default, but can be enabled by assigning a client policy.</span></span>

<div>

## <a name="hide-my-picture"></a><span data-ttu-id="e3fa7-205">Ocultar minha imagem</span><span class="sxs-lookup"><span data-stu-id="e3fa7-205">Hide my picture</span></span>

<span data-ttu-id="e3fa7-206">As configurações para fotos do usuário estão na caixa de diálogo **Opções** no Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-206">Settings for user photos are on the **Options** dialog in Lync 2013.</span></span> <span data-ttu-id="e3fa7-207">Quando você escolhe **ocultar minha imagem**, nenhuma foto do usuário é exibida para você no cliente do Lync, mas sua foto ainda é exibida no seu cartão de visita e fora do Lync.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-207">When you choose **Hide my picture**, no user photo is displayed for you in Lync client, but your photo is still displayed on your contact card and outside of Lync.</span></span>

</div>

<div>

## <a name="show-my-picture"></a><span data-ttu-id="e3fa7-208">Mostrar minha imagem</span><span class="sxs-lookup"><span data-stu-id="e3fa7-208">Show my picture</span></span>

<span data-ttu-id="e3fa7-209">Quando você escolhe a opção **mostrar minha imagem** , sua foto do usuário é exibida no seu cliente do Lync e para outros usuários nas conversas do Lync.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-209">When you choose the **Show my picture** option, your user photo is displayed in your Lync client and to other users in Lync conversations.</span></span> <span data-ttu-id="e3fa7-210">A imagem usada é aquela armazenada no AD DS.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-210">The image used is the one stored in AD DS.</span></span>

</div>

<div>

## <a name="show-a-picture-from-a-website"></a><span data-ttu-id="e3fa7-211">Mostrar uma imagem de um site</span><span class="sxs-lookup"><span data-stu-id="e3fa7-211">Show a picture from a website</span></span>

<span data-ttu-id="e3fa7-212">A opção **Mostrar imagem de um site** torna-se disponível no Lync 2013 depois que uma política de cliente é definida para habilitá-la.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-212">The **Show picture from a website** option becomes available in Lync 2013 after a client policy is set to enable it.</span></span> <span data-ttu-id="e3fa7-213">A versão do cliente deve ser mais recente do que o 15.0.4535.1002, que é instalado com as [atualizações cumulativas do Lync: novembro de 2013](http://go.microsoft.com/fwlink/p/?linkid=509908).</span><span class="sxs-lookup"><span data-stu-id="e3fa7-213">The client version must be newer than 15.0.4535.1002, which is installed with the [Lync Cumulative Updates: November 2013](http://go.microsoft.com/fwlink/p/?linkid=509908).</span></span> <span data-ttu-id="e3fa7-214">Os usuários podem precisar fazer logout e, em seguida, retornar novamente para ver as alterações no cliente.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-214">Users may need to log out and then back in again to see the changes in the client.</span></span>

<span data-ttu-id="e3fa7-215">Você pode definir a política de cliente para habilitar a opção **Mostrar imagem de uma configuração de site** executando a política [set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) no Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-215">You can set the client policy to enable to **Show picture from a website** setting by running the [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) policy in the Lync Server Management Shell.</span></span> <span data-ttu-id="e3fa7-216">Os cmdlets de exemplo a seguir demonstram como definir a política globalmente para todos os usuários em sua implantação:</span><span class="sxs-lookup"><span data-stu-id="e3fa7-216">The following example cmdlets demonstrate how to set the policy globally for all users in your deployment:</span></span>

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


<span data-ttu-id="e3fa7-217">Quando uma imagem é carregada para a caixa de correio do usuário, o Exchange cria automaticamente uma versão de resolução mais baixa da imagem que pode ser usada em aplicativos cliente.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-217">When an image is uploaded to the user’s mailbox, Exchange automatically creates a lower resolution version of the image which can be used in client applications.</span></span> <span data-ttu-id="e3fa7-218">A foto do usuário também é atualizada no AD DS.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-218">The user photo is also updated in AD DS.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="e3fa7-219">Quando um arquivo de imagem é atualizado no AD DS, uma imagem de 48 x 48 pixel é criada e usada para o thumbnailPhoto no AD DS.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-219">When an image file is updated in AD DS, a 48 x 48 pixel image is created and used for the thumbnailPhoto in AD DS.</span></span> <span data-ttu-id="e3fa7-220">Qualquer imagem existente será substituída.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-220">Any existing image is replaced.</span></span> <span data-ttu-id="e3fa7-221">Portanto, se você adicionou uma imagem 96 x 96 ao AD DS, ela será substituída pela nova imagem do 48 x 48.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-221">So if you added a 96 x 96 image to AD DS, it will be overwritten with the new 48 x 48 image.</span></span> <span data-ttu-id="e3fa7-222">Isso é importante apenas que você tem usuários em seu ambiente usando clientes do Lync 2010, pois esses clientes obterão fotos de usuários do AD DS.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-222">This is only important is you have users in your environment using Lync 2010 clients, as those clients will obtain user photos from AD DS.</span></span> <span data-ttu-id="e3fa7-223">Você pode importar imagens de 96 x 96 pixels para substituir aquelas criadas pelo AD DS se você tiver clientes do Lync 2010 em sua organização.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-223">You can import 96 x 96 pixel images to replace the ones created by AD DS if you have Lync 2010 clients in your organization.</span></span>



</div>

</div>

<div>

## <a name="user-photo-support-in-lync-2013"></a><span data-ttu-id="e3fa7-224">Suporte a fotos do usuário no Lync 2013</span><span class="sxs-lookup"><span data-stu-id="e3fa7-224">User photo support in Lync 2013</span></span>

<span data-ttu-id="e3fa7-225">No Lync 2013, há suporte para três resoluções de imagens para fotos do usuário, conforme descrito na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-225">In Lync 2013, three image resolutions are supported for user photos as described in the following table.</span></span> <span data-ttu-id="e3fa7-226">A imagem que é usada é determinada pela configuração de política do cliente atribuída aos usuários do Lync.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-226">The image that is used is determined by the client policy setting assigned to Lync users.</span></span> <span data-ttu-id="e3fa7-227">Consulte "Gerenciando fotos do usuário com cmdlets de política de cliente" neste tópico para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-227">See “Managing user’s photo with Client Policy cmdlets” in this topic for more information.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e3fa7-228">Resolução da imagem (pixels)</span><span class="sxs-lookup"><span data-stu-id="e3fa7-228">Image resolution (pixels)</span></span></th>
<th><span data-ttu-id="e3fa7-229">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="e3fa7-229">Application</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e3fa7-230">48 x 48</span><span class="sxs-lookup"><span data-stu-id="e3fa7-230">48 x 48</span></span></p></td>
<td><p><span data-ttu-id="e3fa7-231">Usado se nenhuma imagem de resolução mais alta estiver selecionada</span><span class="sxs-lookup"><span data-stu-id="e3fa7-231">Used if no higher resolution image is selected</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3fa7-232">96 x 96</span><span class="sxs-lookup"><span data-stu-id="e3fa7-232">96 x 96</span></span></p></td>
<td><p><span data-ttu-id="e3fa7-233">Usado no Outlook Web App e no Outlook 2013</span><span class="sxs-lookup"><span data-stu-id="e3fa7-233">Used in Outlook Web App and Outlook 2013</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3fa7-234">648 x 648</span><span class="sxs-lookup"><span data-stu-id="e3fa7-234">648 x 648</span></span></p></td>
<td><p><span data-ttu-id="e3fa7-235">Usado no cliente da área de trabalho do Lync 2013 e no Lync 2013 Web App</span><span class="sxs-lookup"><span data-stu-id="e3fa7-235">Used in Lync 2013 desktop client and Lync 2013 Web App</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e3fa7-236">Qualquer usuário com uma caixa de correio habilitada no Exchange 2013 pode carregar uma imagem diferente, incluindo fotos de alta resolução, através do Outlook Web Access ou do Lync 2013 cliente opções.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-236">Any user with a mailbox enabled in Exchange 2013 can upload a different image, including high-resolution photos, through Outlook Web Access or Lync 2013 client options.</span></span> <span data-ttu-id="e3fa7-237">As configurações recomendadas para imagens usadas incluem:</span><span class="sxs-lookup"><span data-stu-id="e3fa7-237">The recommended settings for images used include:</span></span>

  - <span data-ttu-id="e3fa7-238">**Resolução de imagem**   648 por 648 pixels</span><span class="sxs-lookup"><span data-stu-id="e3fa7-238">**Image Resolution**   648 by 648 pixels</span></span>

  - <span data-ttu-id="e3fa7-239">**Profundidade de cor**   de 24 bits</span><span class="sxs-lookup"><span data-stu-id="e3fa7-239">**Color Depth**   24-bit</span></span>

  - <span data-ttu-id="e3fa7-240">**Tamanho do arquivo de imagem**   de até 20 MB</span><span class="sxs-lookup"><span data-stu-id="e3fa7-240">**Image file size**   up to 20 MB</span></span>

  - <span data-ttu-id="e3fa7-241">**Formato de arquivo**   JPEG</span><span class="sxs-lookup"><span data-stu-id="e3fa7-241">**File format**   JPEG</span></span>

<span data-ttu-id="e3fa7-242">Uma imagem JPEG típica de 24 bits de 648 pixels por 648 pixels tem um tamanho de arquivo de aproximadamente 240 KB, portanto, 1 MB de espaço de armazenamento é necessário para cada 4 fotos do usuário.</span><span class="sxs-lookup"><span data-stu-id="e3fa7-242">A typical 24-bit JPEG image that is 648 pixels by 648 pixels has a file size of about 240 KB, so 1 MB of storage space is needed for every 4 user photos.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

