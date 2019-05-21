---
title: Configurar o uso de fotos de alta resolução no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 995da78a-dc44-45a3-908d-16fe36cfa0d9
description: 'Resumo: configurar o uso de fotos de alta resolução no Exchange Server 2016 ou no Exchange Server 2013 e no Skype for Business Server.'
ms.openlocfilehash: d52cdb2d84fedba0dcbec97cbca4074b1ae12a84
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34278203"
---
# <a name="configure-the-use-of-high-resolution-photos-in-skype-for-business-server"></a><span data-ttu-id="98c3a-103">Configurar o uso de fotos de alta resolução no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="98c3a-103">Configure the use of high-resolution photos in Skype for Business Server</span></span>
 
<span data-ttu-id="98c3a-104">**Resumo:** Configurar o uso de fotos de alta resolução no Exchange Server 2016 ou no Exchange Server 2013 e no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="98c3a-104">**Summary:** Configure the use of high-resolution photos in Exchange Server 2016 or Exchange Server 2013 and Skype for Business Server.</span></span>
  
<span data-ttu-id="98c3a-105">As fotos do Skype for Business Server podem ser armazenadas em uma caixa de correio do Exchange Server 2016 ou do Exchange Server 2013 do usuário, o que permite tamanhos de fotos de até 648 pixels por 648 pixels.</span><span class="sxs-lookup"><span data-stu-id="98c3a-105">In Skype for Business Server photos can be stored in a user's Exchange Server 2016 or Exchange Server 2013 mailbox, which allows for photo sizes up to 648 pixels by 648 pixels.</span></span> <span data-ttu-id="98c3a-106">Além disso, o Exchange Server pode redimensionar automaticamente essas fotos para uso em diferentes produtos, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="98c3a-106">In addition, Exchange Server can automatically resize these photos for use in different products as needed.</span></span> <span data-ttu-id="98c3a-107">Geralmente, isso significa três tamanhos e resoluções de fotos diferentes.</span><span class="sxs-lookup"><span data-stu-id="98c3a-107">Typically that means three different photo sizes and resolutions:</span></span>
  
- <span data-ttu-id="98c3a-108">64 pixels por 64 pixels, o tamanho utilizado pelo atributo thumbnailPhoto do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="98c3a-108">64 pixels by 64 pixels, the size used for the Active Directory thumbnailPhoto attribute.</span></span> <span data-ttu-id="98c3a-109">Se você carregar uma foto no Exchange Server, o Exchange criará automaticamente uma versão de 64 pixel por 64 pixels dessa foto e atualizará o atributo thumbnailPhoto do usuário.</span><span class="sxs-lookup"><span data-stu-id="98c3a-109">If you upload a photo to Exchange Server, Exchange will automatically create a 64 pixel by 64 pixel version of that photo and update the user's thumbnailPhoto attribute.</span></span> <span data-ttu-id="98c3a-110">Observe, porém, que o inverso não é verdadeiro: se você atualizar manualmente o atributo thumbnailPhoto no Active Directory, a foto na caixa de correio do Exchange do usuário não será atualizada automaticamente.</span><span class="sxs-lookup"><span data-stu-id="98c3a-110">Note, however, that the reverse is not true: if you manually update the thumbnailPhoto attribute in Active Directory the photo in the user's Exchange mailbox will not automatically be updated.</span></span>
    
- <span data-ttu-id="98c3a-111">96 pixels por 96 pixels, para uso no Microsoft Outlook 2013 Web App, Microsoft Outlook 2013, Skype for Business Web App e Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="98c3a-111">96 pixels by 96 pixels, for use in Microsoft Outlook 2013 Web App, Microsoft Outlook 2013, Skype for Business Web App, and Skype for Business.</span></span>
    
- <span data-ttu-id="98c3a-112">648 pixels por 648 pixels para uso no Skype for Business e no Skype for Business Web App Web App.</span><span class="sxs-lookup"><span data-stu-id="98c3a-112">648 pixels by 648 pixels for use in Skype for Business and Skype for Business Web App Skype for Business Web App.</span></span>
    
> [!NOTE]
> <span data-ttu-id="98c3a-113">Se você tiver os recursos, é recomendável carregar 648 x 648 fotos; Isso fornece a resolução máxima e a qualidade de imagem ideal em qualquer um dos aplicativos do Office 2013.</span><span class="sxs-lookup"><span data-stu-id="98c3a-113">If you have the resources, it is recommended that you upload 648 x 648 photos; that provides the maximum resolution and optimal picture quality in any of the Office 2013 applications.</span></span> <span data-ttu-id="98c3a-114">Cada foto JPEG com um tamanho de 648 x 648 e uma profundidade de 24 bits resulta em um tamanho de arquivo de aproximadamente 240 kilobytes.</span><span class="sxs-lookup"><span data-stu-id="98c3a-114">Each JPEG photo with a size of 648 x 648 and a depth of 24 bits results in a file size of approximately 240 kilobytes.</span></span> <span data-ttu-id="98c3a-115">Isso significa que você precisará de aproximadamente 1 megabyte de espaço em disco para cada 4 fotos de usuário.</span><span class="sxs-lookup"><span data-stu-id="98c3a-115">That means you will need approximately 1 megabyte of disk space for every 4 user photos.</span></span> 
  
<span data-ttu-id="98c3a-116">Fotos de alta resolução, que são acessadas usando serviços Web do Exchange, podem ser carregadas pelos usuários que executam o Outlook 2013 Web App; os usuários só têm permissão para atualizar sua própria foto.</span><span class="sxs-lookup"><span data-stu-id="98c3a-116">High-resolution photos, which are accessed by using Exchange Web Services, can be uploaded by users who are running Outlook 2013 Web App; users are only allowed to update their own photo.</span></span> <span data-ttu-id="98c3a-117">No entanto, os administradores podem atualizar a foto para qualquer usuário usando o Shell de gerenciamento do Exchange e vários comandos do Windows PowerShell semelhantes ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="98c3a-117">Administrators, however, can update the photo for any user by using the Exchange Management Shell and a series of Windows PowerShell commands similar to the following:</span></span>
  
```
$photo = ([Byte[]] $(Get-Content -Path "C:\Photos\Kenmyer.jpg" -Encoding Byte -ReadCount 0))
Set-UserPhoto -Identity "Ken Myer" -PictureData $photo -Preview -Confirm:$False
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

<span data-ttu-id="98c3a-118">O primeiro comando no exemplo anterior usa o `Get-Content` cmdlet para ler o conteúdo do arquivo C:\Photos\Kenmyer.jpg e armazenar esses dados em uma variável chamada $Photo.</span><span class="sxs-lookup"><span data-stu-id="98c3a-118">The first command in the preceding example uses the `Get-Content` cmdlet to read the contents of the file C:\Photos\Kenmyer.jpg and store that data in a variable named $photo.</span></span> <span data-ttu-id="98c3a-119">No segundo comando, o cmdlet `Set-UserPhoto` do Exchange é usado para carregar a foto e anexar essa foto à conta de usuário de Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="98c3a-119">In the second command, the Exchange cmdlet `Set-UserPhoto` is used to upload the photo and attach that photo to Ken Myer's user account.</span></span>
  
> [!NOTE]
> <span data-ttu-id="98c3a-120">Neste exemplo, o nome de exibição do Active Directory de Ken Myer é usado como a identidade da conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="98c3a-120">In this example, Ken Myer's Active Directory display name is used as the user account Identity.</span></span> <span data-ttu-id="98c3a-121">Você também pode referenciar uma conta de usuário usando outros identificadores como endereço SMTP do usuário ou seu nome principal de usuário.</span><span class="sxs-lookup"><span data-stu-id="98c3a-121">You can also reference a user account by using other identifiers such as the user's SMTP address or his or her User Principal Name.</span></span> <span data-ttu-id="98c3a-122">Consulte a documentação do cmdlet Set-UserPhoto em [https://go.microsoft.com/fwlink/p/?LinkId=268536](https://go.microsoft.com/fwlink/p/?LinkId=268536) para obter mais informações</span><span class="sxs-lookup"><span data-stu-id="98c3a-122">See the documentation for the Set-UserPhoto cmdlet at [https://go.microsoft.com/fwlink/p/?LinkId=268536](https://go.microsoft.com/fwlink/p/?LinkId=268536) for more information</span></span>
  
<span data-ttu-id="98c3a-p107">Carregar a foto não é o mesmo que atribuir essa foto à conta de usuário de Ken Myer. Em vez disso, carregar a foto simplesmente resulta em uma visualização da foto a ser exibida na página Opções do Outlook Web App. Para realmente atribuir essa foto à conta de usuário, o usuário deve clicar em **Salvar**, na página Opções, ou o administrador deve executar o terceiro comando do exemplo. Esse terceiro comando usa o parâmetro Salvar para atribuir a foto à conta de usuário de Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="98c3a-p107">Uploading the photo does not equate to assigning that photo to Ken Myer's user account. Instead, uploading the photo simply results in a preview of that photo to be displayed on the Outlook Web App Options page. To actually assign that photo to the user account the user must click **Save** on the Options page or the administrator must execute the third command in the example. That third command uses the Save parameter to assign the photo to Ken Myer's user account:</span></span>
  
```
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

<span data-ttu-id="98c3a-127">Para verificar se a nova foto foi atribuída à conta de usuário, Ken Myer pode fazer logon no Skype for Business, selecionar **Opções**e, em seguida, selecionar **minha imagem**.</span><span class="sxs-lookup"><span data-stu-id="98c3a-127">To verify that the new photo has been assigned to the user account, Ken Myer can log on to Skype for Business, select **Options**, and then select **My Picture**.</span></span> <span data-ttu-id="98c3a-128">A foto recém-carregada deve ser exibida como a foto pessoal de Ken.</span><span class="sxs-lookup"><span data-stu-id="98c3a-128">The newly-uploaded photo should be displayed as Ken's personal photo.</span></span> <span data-ttu-id="98c3a-129">Como alternativa, os administradores podem verificar a foto de qualquer usuário iniciando o Internet Explorer e navegando até uma URL parecida com esta:</span><span class="sxs-lookup"><span data-stu-id="98c3a-129">Alternatively, administrators can verify the photo for any user by starting Internet Explorer and navigating to a URL similar to this:</span></span>
  
```
https://atl-mail-001.litwareinc.com/ews/Exchange.asmx/s/GetUserPhoto?email=kenmyer@litwareinc.com&amp;size=HR648x648
```

<span data-ttu-id="98c3a-130">Se o administrador puder ver a foto usando o Internet Explorer, mas o usuário não puder ver sua foto no Skype for Business, talvez haja um problema de conectividade com os serviços Web do Exchange ou com o serviço de descoberta automática do Exchange.</span><span class="sxs-lookup"><span data-stu-id="98c3a-130">If the administrator can view the photo using Internet Explorer but the user cannot view his or her photo in Skype for Business there may be a connectivity problem with Exchange Web Services or with the Exchange autodiscover service.</span></span>
  
<span data-ttu-id="98c3a-131">Observe também que nenhuma configuração adicional é necessária para disponibilizar essa foto no Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="98c3a-131">Note, too that no additional configuration is required in order to make this photo available in Skype for Business.</span></span> <span data-ttu-id="98c3a-132">Em vez disso, a foto estará disponível instantaneamente após o carregamento e o `Set-UserPhoto` cmdlet tiver sido executado.</span><span class="sxs-lookup"><span data-stu-id="98c3a-132">Instead, the photo will be instantly available after it has been uploaded and the `Set-UserPhoto` cmdlet has been run.</span></span>
