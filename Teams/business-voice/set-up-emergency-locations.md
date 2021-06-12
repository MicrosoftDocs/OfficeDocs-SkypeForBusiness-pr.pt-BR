---
title: Configurar Microsoft 365 Business Voice locais de emergência
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: Saiba como configurar locais de emergência para Microsoft 365 Business Voice.
appliesto:
- Microsoft Teams
ms.openlocfilehash: e8f740034a67e1f2199b5a18aa34d67e16df43e2
ms.sourcegitcommit: 2419348e964cfe97b72d533f267c5d7055d5366f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/11/2021
ms.locfileid: "52907757"
---
# <a name="step-1-set-up-a-business-voice-emergency-location"></a><span data-ttu-id="b8d63-103">Etapa 1: Configurar um local de emergência do Business Voice</span><span class="sxs-lookup"><span data-stu-id="b8d63-103">Step 1: Set up a Business Voice emergency location</span></span>

<span data-ttu-id="b8d63-104">Um local de emergência é usado quando alguém em sua organização chama serviços de emergência, como incêndio, polícia ou ambulância.</span><span class="sxs-lookup"><span data-stu-id="b8d63-104">An emergency location is used when someone in your organization calls emergency services such as fire, police, or ambulance.</span></span> <span data-ttu-id="b8d63-105">Quando uma pessoa chama um serviço de emergência, o endereço configurado como endereço de emergência da sua organização é enviado para o serviço.</span><span class="sxs-lookup"><span data-stu-id="b8d63-105">When a person calls an emergency service, the address that's configured as your organization's emergency address is sent to the service.</span></span> <span data-ttu-id="b8d63-106">Esta etapa configura o local de emergência principal para sua organização.</span><span class="sxs-lookup"><span data-stu-id="b8d63-106">This step sets up the primary emergency location for your organization.</span></span> <span data-ttu-id="b8d63-107">Esse local será associado ao número de telefone principal da sua empresa em uma etapa posterior.</span><span class="sxs-lookup"><span data-stu-id="b8d63-107">This location will be associated with your company's main phone number in a later step.</span></span>

<span data-ttu-id="b8d63-108">Se você tiver usuários em vários locais, como home offices ou escritórios em outras cidades, poderá configurar locais de emergência adicionais.</span><span class="sxs-lookup"><span data-stu-id="b8d63-108">If you have users in multiple locations, such as home offices or offices in other cities, you can configure additional emergency locations.</span></span> <span data-ttu-id="b8d63-109">Você pode até mesmo configurar locais específicos em um local.</span><span class="sxs-lookup"><span data-stu-id="b8d63-109">You can even configure specific places within a location.</span></span> <span data-ttu-id="b8d63-110">Os locais podem ser edifícios, pisos, escritórios ou outros locais onde os usuários possam estar em um local.</span><span class="sxs-lookup"><span data-stu-id="b8d63-110">Places can be different buildings, floors, offices, or other places where users may be at a location.</span></span> <span data-ttu-id="b8d63-111">Locais e locais adicionais podem ser adicionados depois que você concluir sua configuração inicial do Business Voice.</span><span class="sxs-lookup"><span data-stu-id="b8d63-111">Additional locations and places can be added after you complete your initial setup of Business Voice.</span></span>

<span data-ttu-id="b8d63-112">O vídeo a seguir mostra como concluir essas etapas no Teams de administração.</span><span class="sxs-lookup"><span data-stu-id="b8d63-112">The following video shows you how to complete these steps in the Teams admin center.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWEZGE]

## <a name="add-an-emergency-location"></a><span data-ttu-id="b8d63-113">Adicionar um local de emergência</span><span class="sxs-lookup"><span data-stu-id="b8d63-113">Add an emergency location</span></span>

1. <span data-ttu-id="b8d63-114">Abra o Microsoft Teams de administração e faça logoff com um usuário que seja um administrador global (geralmente essa é a conta que você usou para se inscrever no Microsoft 365).</span><span class="sxs-lookup"><span data-stu-id="b8d63-114">Open the Microsoft Teams admin center and log in with a user that is a Global admin (this is usually the account you used to sign up for Microsoft 365).</span></span>
1. <span data-ttu-id="b8d63-115">No painel de navegação esquerdo, vá para <a href="https://admin.teams.microsoft.com/locations" target="_blank"> **Locais**  >  **Endereços de emergência**</a>.</span><span class="sxs-lookup"><span data-stu-id="b8d63-115">In the left navigation pane, go to <a href="https://admin.teams.microsoft.com/locations" target="_blank">**Locations** > **Emergency addresses**</a>.</span></span>
1. <span data-ttu-id="b8d63-116">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="b8d63-116">Click **Add**.</span></span>
1. <span data-ttu-id="b8d63-117">Insira um nome e uma descrição para o local.</span><span class="sxs-lookup"><span data-stu-id="b8d63-117">Enter a name and description for the location.</span></span>
1. <span data-ttu-id="b8d63-118">Selecione o país ou a região e insira o endereço.</span><span class="sxs-lookup"><span data-stu-id="b8d63-118">Select the country or region, and then enter the address.</span></span>

   > [!NOTE]
   > <span data-ttu-id="b8d63-119">Na Bélgica, França, Alemanha, Irlanda, Países Baixos e Espanha, é importante entender que, para ativar com êxito um número de telefone no Microsoft 365 ou no Office 365, o endereço definido no local de emergência, que é usado para adquirir o número, deve corresponder ao código de área do número de telefone.</span><span class="sxs-lookup"><span data-stu-id="b8d63-119">In Belgium, France, Germany, Ireland, Netherlands, and Spain, it's important to understand that to successfully activate a phone number in Microsoft 365 or Office 365, the address set up in the emergency location, which is used to acquire the number, must match the phone number's area code.</span></span>

1. <span data-ttu-id="b8d63-120">Se o endereço não for encontrado e você quiser editar manualmente o endereço, a opção **Editar o endereço manualmente.**</span><span class="sxs-lookup"><span data-stu-id="b8d63-120">If the address isn't found and you want to manually edit the address, turn on **Edit the address manually**.</span></span>
1. <span data-ttu-id="b8d63-121">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="b8d63-121">Click **Save**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="b8d63-122">Próxima etapa: Configurar números de telefone</span><span class="sxs-lookup"><span data-stu-id="b8d63-122">Next step: Set up phone numbers</span></span>](set-up-phone-numbers.md)
