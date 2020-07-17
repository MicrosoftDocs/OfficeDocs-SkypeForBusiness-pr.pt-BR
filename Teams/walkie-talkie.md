---
title: Aplicativo faça talkie no Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Como configurar o aplicativo faça talkie no Microsoft Teams, a partir de uma perspectiva ITAdmin.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9369cf56a32142d6527fcb86271d8d0fa56718ec
ms.sourcegitcommit: 2467ece95e100a3a3cc2be3538d8eb7d878b3663
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/06/2020
ms.locfileid: "45043003"
---
# <a name="walkie-talkie-app-in-microsoft-teams"></a><span data-ttu-id="ea21a-103">Aplicativo faça de conversas no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ea21a-103">Walkie Talkie app in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="ea21a-104">O aplicativo faça talkie no Teams oferece comunicação instantânea Push-to-Talk (PTT) para a sua equipe e em breve estará disponível no modo de visualização pública no Android.</span><span class="sxs-lookup"><span data-stu-id="ea21a-104">The Walkie Talkie app in Teams provides instant push-to-talk (PTT) communication for your team and will soon be available in Public Preview on Android.</span></span> <span data-ttu-id="ea21a-105">O faça talkie permite que os usuários se conectem com sua equipe usando os mesmos canais subjacentes dos quais são membros.</span><span class="sxs-lookup"><span data-stu-id="ea21a-105">Walkie Talkie allows users to connect with their team using the same underlying channels they're members of.</span></span> <span data-ttu-id="ea21a-106">Somente os usuários que se conectam ao faça talkie em um canal tornam-se participantes e podem se comunicar uns com os outros usando o push para conversar, um por vez.</span><span class="sxs-lookup"><span data-stu-id="ea21a-106">Only users who connect to Walkie Talkie in a channel become participants and can communicate with each other using push-to-talk, one at a time.</span></span>

<span data-ttu-id="ea21a-107">Com o faça de trabalho no Microsoft Teams, os trabalhadores de primeira mão podem se comunicar com uma experiência PTT conhecida sem precisar ter rádios em massa, e o faça de fala funciona em qualquer lugar com conexão WiFi ou celular à Internet.</span><span class="sxs-lookup"><span data-stu-id="ea21a-107">With Walkie Talkie in Teams, firstline workers can now securely communicate with a familiar PTT experience without needing to carry bulky radios, and Walkie Talkie works anywhere with WiFi or cellular internet connectivity.</span></span>

## <a name="getting-started"></a><span data-ttu-id="ea21a-108">Introdução</span><span class="sxs-lookup"><span data-stu-id="ea21a-108">Getting started</span></span>

### <a name="deploying-walkie-talkie"></a><span data-ttu-id="ea21a-109">Implantando o faça talkie</span><span class="sxs-lookup"><span data-stu-id="ea21a-109">Deploying Walkie Talkie</span></span>

<span data-ttu-id="ea21a-110">Durante a visualização pública, o faça talkie não está pré-instalado.</span><span class="sxs-lookup"><span data-stu-id="ea21a-110">During the Public Preview, Walkie Talkie is not pre-installed.</span></span> <span data-ttu-id="ea21a-111">Para habilitar esse recurso para os usuários de sua organização, você precisa adicionar faça a [política de configuração do aplicativo](teams-app-setup-policies.md)   atribuída a usuários do centro de [Administração do teams](https://admin.teams.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="ea21a-111">To enable this feature for users in your organization, you need to add Walkie Talkie to the [App Setup Policy](teams-app-setup-policies.md) assigned to users from the [Teams Admin Center](https://admin.teams.microsoft.com/).</span></span>

<span data-ttu-id="ea21a-112">Uma vez habilitada, o faça talkie estará disponível no aplicativo Android em 48 horas.</span><span class="sxs-lookup"><span data-stu-id="ea21a-112">Once enabled, Walkie Talkie will become available on the Android app within 48 hours.</span></span>

### <a name="adding-walkie-talkie-to-your-app-list"></a><span data-ttu-id="ea21a-113">Adicionando o faça Talkse à sua lista de aplicativos</span><span class="sxs-lookup"><span data-stu-id="ea21a-113">Adding Walkie Talkie to your app list</span></span>

<span data-ttu-id="ea21a-114">No centro de administração do Microsoft Teams, em políticas de configuração do **aplicativo do teams**  >  **Setup policies**, você deve **permitir a fixação do usuário** definida como **ativado**.</span><span class="sxs-lookup"><span data-stu-id="ea21a-114">In the Microsoft Teams admin center, under **Teams app** > **Setup policies**, you should have **Allow user pinning** set to **On**.</span></span> <span data-ttu-id="ea21a-115">Em seguida, na seção aplicativos fixos, clique em **+ adicionar aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="ea21a-115">Then, under the Pinned Apps section, click **+Add Apps**.</span></span>

:::image type="content" source="media/deploy-walkie-talkie-1.png" alt-text="Mostra a seção de aplicativos fixos e o botão adicionar aplicativos a ser selecionado.":::

<span data-ttu-id="ea21a-117">No painel **adicionar aplicativos fixos** que aparece à direita, use a caixa de texto de **pesquisa** para procurar faça fala.</span><span class="sxs-lookup"><span data-stu-id="ea21a-117">On the **Add pinned apps** panel that appears on the right, use the **Search** textbox to look for Walkie Talkie.</span></span> <span data-ttu-id="ea21a-118">Quando você tiver um resultado de pesquisa, clique no botão **Adicionar** à direita do nome para adicioná-lo à sua lista.</span><span class="sxs-lookup"><span data-stu-id="ea21a-118">When you have it as a search result, click the **Add** button to the right of the name to add it to your list.</span></span>

:::image type="content" source="media/deploy-walkie-talkie-2.png" alt-text="Mostra a barra lateral adicionar aplicativos fixos com faça inserida no painel de pesquisa e o aplicativo de fala do faça nos resultados da pesquisa, com o botão Adicionar ao lado dele.":::

<span data-ttu-id="ea21a-120">O aplicativo faça talkie agora deve aparecer na lista de aplicativos fixos e estar disponível para ser usado quando você clicar no botão **salvar** .</span><span class="sxs-lookup"><span data-stu-id="ea21a-120">The Walkie Talkie app should now appear on the Pinned Apps list, and be available for use once you click the **Save** button.</span></span>

:::image type="content" source="media/deploy-walkie-talkie-3.png" alt-text="Mostra a lista de aplicativos fixos com o aplicativo de faça de fala adicionado e o botão salvar abaixo da lista.":::

### <a name="network-documentation"></a><span data-ttu-id="ea21a-122">Documentação da rede</span><span class="sxs-lookup"><span data-stu-id="ea21a-122">Network documentation</span></span>

<span data-ttu-id="ea21a-123">O faça Talk in Teams requer conectividade à Internet e as condições de rede abaixo delas são necessárias para obter a melhor experiência possível.</span><span class="sxs-lookup"><span data-stu-id="ea21a-123">Walkie Talkie in Teams requires Internet connectivity and below the network conditions are required for optimal experience.</span></span>

<span data-ttu-id="ea21a-124">Latência (RTT) < 300ms | < de Tremulação do 30ms | Perda de pacotes < 1%</span><span class="sxs-lookup"><span data-stu-id="ea21a-124">Latency (RTT) < 300ms | Jitter < 30ms | Packet Loss < 1%</span></span>

<span data-ttu-id="ea21a-125">Conforme observado acima, a qualidade da mídia em tempo real em uma rede IP é bastante afetada pela qualidade da conectividade de rede, mas especialmente pela quantidade de:</span><span class="sxs-lookup"><span data-stu-id="ea21a-125">As noted above, the quality of real-time media over an IP network is greatly impacted by the quality of the network connectivity, but especially by the amount of:</span></span>

- <span data-ttu-id="ea21a-126">**Latência** -é o tempo que leva para obter um pacote IP do ponto a ao ponto B na rede.</span><span class="sxs-lookup"><span data-stu-id="ea21a-126">**Latency** - This is the time it takes to get an IP packet from point A to point B on the network.</span></span> <span data-ttu-id="ea21a-127">Esse atraso de propagação de rede está essencialmente ligado à distância física entre os dois pontos e a velocidade da luz, incluindo a sobrecarga adicional sofrida pelos vários roteadores intermediários.</span><span class="sxs-lookup"><span data-stu-id="ea21a-127">This network propagation delay is essentially tied to physical distance between the two points and the speed of light, including additional overhead taken by the various routers in between.</span></span> <span data-ttu-id="ea21a-128">A latência é medida como RTT (tempo de ida e volta).</span><span class="sxs-lookup"><span data-stu-id="ea21a-128">Latency is measured as Round-trip Time (RTT).</span></span>
- <span data-ttu-id="ea21a-129">**Perda de pacote** -geralmente é definido como uma porcentagem de pacotes perdidos em uma determinada janela de tempo.</span><span class="sxs-lookup"><span data-stu-id="ea21a-129">**Packet Loss** - This is often defined as a percentage of packets that are lost in a given window of time.</span></span> <span data-ttu-id="ea21a-130">A perda de pacotes afeta diretamente a qualidade do áudio, desde pequenos pacotes perdidos individuais com quase nenhum impacto, até perdas de Burst back-to-back que causam o recorte de áudio completo.</span><span class="sxs-lookup"><span data-stu-id="ea21a-130">Packet loss directly affects audio quality—from small, individual lost packets having almost no impact, to back-to-back burst losses that cause complete audio cut-out.</span></span>
- <span data-ttu-id="ea21a-131">**Tremulação** -esta é a alteração média em atraso entre pacotes sucessivos.</span><span class="sxs-lookup"><span data-stu-id="ea21a-131">**Jitter** - This is the average change in delay between successive packets.</span></span>

<span data-ttu-id="ea21a-132">O uso de dados esperado do faça talkie é cerca de 20KB/s ao enviar ou receber áudio.</span><span class="sxs-lookup"><span data-stu-id="ea21a-132">Expected data usage from Walkie Talkie is around 20KB/s when sending or receiving audio.</span></span> <span data-ttu-id="ea21a-133">Quando ocioso, o uso esperado de dados de faça de é insignificant.</span><span class="sxs-lookup"><span data-stu-id="ea21a-133">When idle, expected data usage from Walkie Talkie is negligible.</span></span>

### <a name="walkie-talkie-devices"></a><span data-ttu-id="ea21a-134">Dispositivos faça de fala</span><span class="sxs-lookup"><span data-stu-id="ea21a-134">Walkie Talkie devices</span></span>

<span data-ttu-id="ea21a-135">Em geral, os funcionários de primeira mão precisam falar e receber chamadas do faça Talk, mesmo quando seus telefones estiverem bloqueados.</span><span class="sxs-lookup"><span data-stu-id="ea21a-135">FirstLine workers often need to speak and receive Walkie Talkie calls even when their phones are locked.</span></span> <span data-ttu-id="ea21a-136">Essa experiência é possível por meio de dispositivos especializados com um botão PTT dedicado.</span><span class="sxs-lookup"><span data-stu-id="ea21a-136">This experience is possible through specialized devices with a dedicated PTT button.</span></span>

- <span data-ttu-id="ea21a-137">Telefones existentes</span><span class="sxs-lookup"><span data-stu-id="ea21a-137">Existing phones</span></span>
  - <span data-ttu-id="ea21a-138">Fone de ouvido com microfone com fio ([Klein eletrônicos](https://www.kleinelectronics.com/))</span><span class="sxs-lookup"><span data-stu-id="ea21a-138">Wired headsets ([Klein Electronics](https://www.kleinelectronics.com/))</span></span>
  - <span data-ttu-id="ea21a-139">Fones de ouvido sem fio ([Jabra BlueParrott](https://www.blueparrott.com/))</span><span class="sxs-lookup"><span data-stu-id="ea21a-139">Wireless headsets ([Jabra BlueParrott](https://www.blueparrott.com/))</span></span>
- <span data-ttu-id="ea21a-140">Telefones resistentes</span><span class="sxs-lookup"><span data-stu-id="ea21a-140">Rugged phones</span></span>
  - <span data-ttu-id="ea21a-141">Samsung Galaxy XCover pro</span><span class="sxs-lookup"><span data-stu-id="ea21a-141">Samsung Galaxy XCover Pro</span></span>
    - <span data-ttu-id="ea21a-142">[Mais informações](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/).</span><span class="sxs-lookup"><span data-stu-id="ea21a-142">[More info](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/).</span></span>
    - <span data-ttu-id="ea21a-143">[Guia de configuração](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm).</span><span class="sxs-lookup"><span data-stu-id="ea21a-143">[Setup guide](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm).</span></span>

> [!NOTE]
> <span data-ttu-id="ea21a-144">Esses dispositivos não são certificados para equipes.</span><span class="sxs-lookup"><span data-stu-id="ea21a-144">These devices are not Teams certified.</span></span> <span data-ttu-id="ea21a-145">Elas foram validadas para trabalhar com o Microsoft Teams faça de conversar.</span><span class="sxs-lookup"><span data-stu-id="ea21a-145">They have been validated to work with Teams Walkie Talkie.</span></span>

### <a name="license-requirements"></a><span data-ttu-id="ea21a-146">Requisitos de licença</span><span class="sxs-lookup"><span data-stu-id="ea21a-146">License requirements</span></span>

<span data-ttu-id="ea21a-147">O aplicativo faça talkie está incluído em todas as licenças pagas do teams nas [assinaturas do Office 365](https://docs.microsoft.com/MicrosoftTeams/office-365-licensing).</span><span class="sxs-lookup"><span data-stu-id="ea21a-147">Walkie Talkie app is included in all paid licenses of Teams in [Office 365 subscriptions](https://docs.microsoft.com/MicrosoftTeams/office-365-licensing).</span></span> <span data-ttu-id="ea21a-148">Para obter mais informações sobre como obter o Microsoft Teams, confira [como faço para obter acesso ao Microsoft Teams](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)?</span><span class="sxs-lookup"><span data-stu-id="ea21a-148">For more information about getting Teams, check out [How do I get access to Microsoft Teams](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)?</span></span>

> [!NOTE]
> <span data-ttu-id="ea21a-149">Certos recursos avançados podem exigir licenciamento adicional.</span><span class="sxs-lookup"><span data-stu-id="ea21a-149">Certain advanced features may require additional licensing.</span></span> <span data-ttu-id="ea21a-150">Por exemplo, a integração com o Samsung Galaxy XCover pro requer uma licença do Knox.</span><span class="sxs-lookup"><span data-stu-id="ea21a-150">For example, integration with Samsung Galaxy XCover Pro requires a Knox license.</span></span>

## <a name="further-information"></a><span data-ttu-id="ea21a-151">Mais informações</span><span class="sxs-lookup"><span data-stu-id="ea21a-151">Further information</span></span>

- <span data-ttu-id="ea21a-152">ITAdmins pode manter o controle sobre quem está usando o faça Talkse através de políticas de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="ea21a-152">ITAdmins can maintain control over who is using Walkie Talkie through App Policies.</span></span>
- <span data-ttu-id="ea21a-153">Se o trabalhador da primeira mão estiver usando dados móveis para se comunicar por meio do Teams, o faça Talkse usará o mesmo método.</span><span class="sxs-lookup"><span data-stu-id="ea21a-153">If your firstline worker is using mobile data to communicate via Teams, Walkie Talkie will use the same method.</span></span>
- <span data-ttu-id="ea21a-154">O faça Talkment deve funcionar bem em situações de pouca largura de banda ou em situações em que seu smartphone está conectado e funcionando.</span><span class="sxs-lookup"><span data-stu-id="ea21a-154">Walkie Talkie should work well in low bandwidth situations, or situations where your smartphone is connected and working.</span></span> <span data-ttu-id="ea21a-155">Façaa a fala não funcionará quando não houver conectividade alguma.</span><span class="sxs-lookup"><span data-stu-id="ea21a-155">Walkie Talkie will not work when there is no connectivity at all.</span></span>

<span data-ttu-id="ea21a-156">Para ler mais sobre a experiência do usuário final, consulte:</span><span class="sxs-lookup"><span data-stu-id="ea21a-156">For further reading on the end-user experience, see:</span></span>

- [<span data-ttu-id="ea21a-157">Introdução ao Teams faça a Palestrat</span><span class="sxs-lookup"><span data-stu-id="ea21a-157">Get started with Teams Walkie Talkie</span></span>](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [<span data-ttu-id="ea21a-158">Comunique-se com sua equipe com o faça talkie</span><span class="sxs-lookup"><span data-stu-id="ea21a-158">Communicate with your team with Walkie Talkie</span></span>](https://support.microsoft.com/office/communicate-with-your-team-in-walkie-talkie-e4342550-5516-4451-b9ec-93166b60f8a4)
