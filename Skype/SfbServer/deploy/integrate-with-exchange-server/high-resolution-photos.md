---
title: Configurar o uso de fotos em alta resolução no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 995da78a-dc44-45a3-908d-16fe36cfa0d9
description: 'Resumo: configure o uso de fotos de alta resolução no Exchange Server 2019, Exchange Server 2016, Exchange Server 2013 ou Exchange Online e Skype for Business Server.'
ms.openlocfilehash: c55e5a90e222ea024dd63f72b26627141b2f113e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834001"
---
# <a name="configure-the-use-of-high-resolution-photos-in-skype-for-business-server"></a><span data-ttu-id="6b058-103">Configurar o uso de fotos em alta resolução no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="6b058-103">Configure the use of high-resolution photos in Skype for Business Server</span></span>
 
<span data-ttu-id="6b058-104">**Resumo:** Configure o uso de fotos em alta resolução no Exchange Server 2019, exchange Server 2016, Exchange Server 2013 ou Exchange Online e Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="6b058-104">**Summary:** Configure the use of high-resolution photos in Exchange Server 2019, Exchange Server 2016, Exchange Server 2013, or Exchange Online and Skype for Business Server.</span></span>
  
<span data-ttu-id="6b058-105">No Skype for Business Server, as fotos podem ser armazenadas na caixa de correio do Exchange Server 2019, Exchange Server 2016, Exchange Server 2013 ou Exchange Online de um usuário, o que permite tamanhos de fotos de até 648 pixels por 648 pixels.</span><span class="sxs-lookup"><span data-stu-id="6b058-105">In Skype for Business Server, photos can be stored in a user's Exchange Server 2019, Exchange Server 2016, Exchange Server 2013, or Exchange Online mailbox, which allows for photo sizes up to 648 pixels by 648 pixels.</span></span> <span data-ttu-id="6b058-106">Além disso, o Exchange Server pode reize automaticamente essas fotos para uso em produtos diferentes, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="6b058-106">In addition, Exchange Server can automatically resize these photos for use in different products as needed.</span></span> <span data-ttu-id="6b058-107">Normalmente, isso significa três tamanhos e resoluções de fotos diferentes:</span><span class="sxs-lookup"><span data-stu-id="6b058-107">Typically that means three different photo sizes and resolutions:</span></span>
  
- <span data-ttu-id="6b058-108">64 pixels por 64 pixels, o tamanho usado para o atributo thumbnailPhoto do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="6b058-108">64 pixels by 64 pixels, the size used for the Active Directory thumbnailPhoto attribute.</span></span> <span data-ttu-id="6b058-109">Se você carregar uma foto no Exchange Server, o Exchange criará automaticamente uma versão de 64 pixels por 64 pixels dessa foto e atualizará o atributo thumbnailPhoto do usuário.</span><span class="sxs-lookup"><span data-stu-id="6b058-109">If you upload a photo to Exchange Server, Exchange will automatically create a 64 pixel by 64 pixel version of that photo and update the user's thumbnailPhoto attribute.</span></span> <span data-ttu-id="6b058-110">Observe, no entanto, que o inverso não é verdadeiro: se você atualizar manualmente o atributo thumbnailPhoto no Active Directory, a foto na caixa de correio do Exchange do usuário não será atualizada automaticamente.</span><span class="sxs-lookup"><span data-stu-id="6b058-110">Note, however, that the reverse is not true: if you manually update the thumbnailPhoto attribute in Active Directory the photo in the user's Exchange mailbox will not automatically be updated.</span></span>
    
- <span data-ttu-id="6b058-111">96 pixels por 96 pixels, para uso no Microsoft Outlook 2013 Web App, Microsoft Outlook 2013, Skype for Business Web App e Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="6b058-111">96 pixels by 96 pixels, for use in Microsoft Outlook 2013 Web App, Microsoft Outlook 2013, Skype for Business Web App, and Skype for Business.</span></span>
    
- <span data-ttu-id="6b058-112">648 pixels por 648 pixels para uso no Skype for Business e no Skype for Business Web App Skype for Business Web App.</span><span class="sxs-lookup"><span data-stu-id="6b058-112">648 pixels by 648 pixels for use in Skype for Business and Skype for Business Web App Skype for Business Web App.</span></span>
    
> [!NOTE]
> <span data-ttu-id="6b058-113">Se você tiver os recursos, é recomendável carregar fotos de 648 x 648; que fornece a resolução máxima e a qualidade de imagem ideal em qualquer um dos aplicativos do Office 2013.</span><span class="sxs-lookup"><span data-stu-id="6b058-113">If you have the resources, it is recommended that you upload 648 x 648 photos; that provides the maximum resolution and optimal picture quality in any of the Office 2013 applications.</span></span> <span data-ttu-id="6b058-114">Cada foto JPEG com um tamanho de 648 x 648 e uma profundidade de 24 bits resulta em um tamanho de arquivo de aproximadamente 240 quilobytes.</span><span class="sxs-lookup"><span data-stu-id="6b058-114">Each JPEG photo with a size of 648 x 648 and a depth of 24 bits results in a file size of approximately 240 kilobytes.</span></span> <span data-ttu-id="6b058-115">Isso significa que você precisará de aproximadamente 1 megabyte de espaço em disco para cada 4 fotos de usuário.</span><span class="sxs-lookup"><span data-stu-id="6b058-115">That means you will need approximately 1 megabyte of disk space for every 4 user photos.</span></span> 
  
<span data-ttu-id="6b058-116">Fotos em alta resolução, que são acessadas usando os Serviços Web do Exchange, podem ser carregadas por usuários que executam o Outlook 2013 Web App; os usuários só têm permissão para atualizar sua própria foto.</span><span class="sxs-lookup"><span data-stu-id="6b058-116">High-resolution photos, which are accessed by using Exchange Web Services, can be uploaded by users who are running Outlook 2013 Web App; users are only allowed to update their own photo.</span></span> <span data-ttu-id="6b058-117">Os administradores, no entanto, podem atualizar a foto de qualquer usuário usando o Shell de Gerenciamento do Exchange e uma série de comandos do Windows PowerShell semelhantes ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="6b058-117">Administrators, however, can update the photo for any user by using the Exchange Management Shell and a series of Windows PowerShell commands similar to the following:</span></span>
  
```powershell
$photo = ([Byte[]] $(Get-Content -Path "C:\Photos\Kenmyer.jpg" -Encoding Byte -ReadCount 0))
Set-UserPhoto -Identity "Ken Myer" -PictureData $photo -Preview -Confirm:$False
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

<span data-ttu-id="6b058-118">O primeiro comando no exemplo anterior usa o cmdlet para ler o conteúdo do arquivo C:\Photos\Kenmyer.jpg e armazenar esses dados em uma variável denominada `Get-Content` $photo.</span><span class="sxs-lookup"><span data-stu-id="6b058-118">The first command in the preceding example uses the `Get-Content` cmdlet to read the contents of the file C:\Photos\Kenmyer.jpg and store that data in a variable named $photo.</span></span> <span data-ttu-id="6b058-119">No segundo comando, o cmdlet do Exchange é usado para carregar a foto e anexá-lo à conta de usuário `Set-UserPhoto` de Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="6b058-119">In the second command, the Exchange cmdlet `Set-UserPhoto` is used to upload the photo and attach that photo to Ken Myer's user account.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6b058-120">Neste exemplo, o nome de exibição do Active Directory de Ken Myer é usado como a Identidade da conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="6b058-120">In this example, Ken Myer's Active Directory display name is used as the user account Identity.</span></span> <span data-ttu-id="6b058-121">Você também pode fazer referência a uma conta de usuário usando outros identificadores, como o endereço SMTP do usuário ou seu Nome Principal de Usuário.</span><span class="sxs-lookup"><span data-stu-id="6b058-121">You can also reference a user account by using other identifiers such as the user's SMTP address or his or her User Principal Name.</span></span> <span data-ttu-id="6b058-122">Consulte a documentação do cmdlet Set-UserPhoto para [https://go.microsoft.com/fwlink/p/?LinkId=268536](https://go.microsoft.com/fwlink/p/?LinkId=268536) obter mais informações</span><span class="sxs-lookup"><span data-stu-id="6b058-122">See the documentation for the Set-UserPhoto cmdlet at [https://go.microsoft.com/fwlink/p/?LinkId=268536](https://go.microsoft.com/fwlink/p/?LinkId=268536) for more information</span></span>
  
<span data-ttu-id="6b058-123">Carregar a foto não significa atribuir essa foto à conta de usuário de Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="6b058-123">Uploading the photo does not equate to assigning that photo to Ken Myer's user account.</span></span> <span data-ttu-id="6b058-124">Em vez disso, carregar a foto simplesmente resulta em uma visualização da foto a ser exibida na página Opções do Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="6b058-124">Instead, uploading the photo simply results in a preview of that photo to be displayed on the Outlook Web App Options page.</span></span> <span data-ttu-id="6b058-125">Para realmente atribuir essa foto à conta  de usuário, o usuário deve clicar em Salvar na página Opções ou o administrador deve executar o terceiro comando no exemplo.</span><span class="sxs-lookup"><span data-stu-id="6b058-125">To actually assign that photo to the user account the user must click **Save** on the Options page or the administrator must execute the third command in the example.</span></span> <span data-ttu-id="6b058-126">Esse terceiro comando usa o parâmetro Save para atribuir a foto à conta de usuário de Ken Myer:</span><span class="sxs-lookup"><span data-stu-id="6b058-126">That third command uses the Save parameter to assign the photo to Ken Myer's user account:</span></span>
  
```powershell
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

<span data-ttu-id="6b058-127">Para verificar se a nova foto foi atribuída à conta de usuário, Ken Myer pode fazer logon no Skype for Business, selecionar Opções e selecionar **Minha Imagem.**</span><span class="sxs-lookup"><span data-stu-id="6b058-127">To verify that the new photo has been assigned to the user account, Ken Myer can log on to Skype for Business, select **Options**, and then select **My Picture**.</span></span> <span data-ttu-id="6b058-128">A foto recém-carregada deve ser exibida como a foto pessoal de Ken.</span><span class="sxs-lookup"><span data-stu-id="6b058-128">The newly-uploaded photo should be displayed as Ken's personal photo.</span></span> <span data-ttu-id="6b058-129">Como alternativa, os administradores podem verificar a foto de qualquer usuário iniciando o Internet Explorer e navegando até uma URL semelhante a esta:</span><span class="sxs-lookup"><span data-stu-id="6b058-129">Alternatively, administrators can verify the photo for any user by starting Internet Explorer and navigating to a URL similar to this:</span></span>
  
```console
https://atl-mail-001.litwareinc.com/ews/Exchange.asmx/s/GetUserPhoto?email=kenmyer@litwareinc.com&size=HR648x648
```

<span data-ttu-id="6b058-130">Se o administrador puder exibir a foto usando o Internet Explorer, mas o usuário não puder exibir sua foto no Skype for Business, pode haver um problema de conectividade com os Serviços Web do Exchange ou com o serviço de descoberta automática do Exchange.</span><span class="sxs-lookup"><span data-stu-id="6b058-130">If the administrator can view the photo using Internet Explorer but the user cannot view his or her photo in Skype for Business there may be a connectivity problem with Exchange Web Services or with the Exchange autodiscover service.</span></span>
  
<span data-ttu-id="6b058-131">Observe também que nenhuma configuração adicional é necessária para disponibilizar essa foto no Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="6b058-131">Note, too that no additional configuration is required in order to make this photo available in Skype for Business.</span></span> <span data-ttu-id="6b058-132">Em vez disso, a foto ficará disponível instantaneamente depois que ela tiver sido carregada e o `Set-UserPhoto` cmdlet tiver sido executado.</span><span class="sxs-lookup"><span data-stu-id="6b058-132">Instead, the photo will be instantly available after it has been uploaded and the `Set-UserPhoto` cmdlet has been run.</span></span>
