---
title: Aplicativo Walkie Talkie no Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Como configurar o aplicativo Walkie Talkie no Microsoft Teams, de uma perspectiva itadmin.
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
ms.openlocfilehash: 63cd853b8a068e7acfc5752e3cd94b5d0102bc2f
ms.sourcegitcommit: 04eba352d9e203aa9cd1282c4f4c7158a0469678
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2021
ms.locfileid: "49944586"
---
# <a name="walkie-talkie-app-in-microsoft-teams"></a><span data-ttu-id="b3df5-103">Aplicativo Walkie Talkie no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b3df5-103">Walkie Talkie app in Microsoft Teams</span></span>

<span data-ttu-id="b3df5-104">O aplicativo Walkie Talkie no Teams fornece comunicação por push-to-talk (PTT) instantânea para sua equipe e agora está disponível no Android.</span><span class="sxs-lookup"><span data-stu-id="b3df5-104">The Walkie Talkie app in Teams provides instant push-to-talk (PTT) communication for your team and is now available on Android.</span></span> <span data-ttu-id="b3df5-105">O Walkie Talkie permite que os usuários se conectem com sua equipe usando os mesmos canais subjacentes dos que são membros.</span><span class="sxs-lookup"><span data-stu-id="b3df5-105">Walkie Talkie allows users to connect with their team using the same underlying channels they're members of.</span></span> <span data-ttu-id="b3df5-106">Somente os usuários que se conectam ao Walkie Talkie em um canal se tornam participantes e podem se comunicar uns com os outros usando o push-to-talk, um de cada vez.</span><span class="sxs-lookup"><span data-stu-id="b3df5-106">Only users who connect to Walkie Talkie in a channel become participants and can communicate with each other using push-to-talk, one at a time.</span></span>

<span data-ttu-id="b3df5-107">Com o Walkie Talkie no Teams, os trabalhadores da linha de frente agora podem se comunicar com segurança com uma experiência de PTT familiar sem precisar carregar rádios em massa, e o Walkie Talkie funciona em qualquer lugar com WiFi ou conectividade com a Internet celular.</span><span class="sxs-lookup"><span data-stu-id="b3df5-107">With Walkie Talkie in Teams, Frontline workers can now securely communicate with a familiar PTT experience without needing to carry bulky radios, and Walkie Talkie works anywhere with WiFi or cellular internet connectivity.</span></span>

## <a name="getting-started"></a><span data-ttu-id="b3df5-108">Introdução</span><span class="sxs-lookup"><span data-stu-id="b3df5-108">Getting started</span></span>

### <a name="deploying-walkie-talkie"></a><span data-ttu-id="b3df5-109">Implantando o Walkie Talkie</span><span class="sxs-lookup"><span data-stu-id="b3df5-109">Deploying Walkie Talkie</span></span>

<span data-ttu-id="b3df5-110">Atualmente, o Walkie Talkie não está pré-instalado.</span><span class="sxs-lookup"><span data-stu-id="b3df5-110">Currently, Walkie Talkie is not pre-installed.</span></span> <span data-ttu-id="b3df5-111">Para habilitar esse recurso para os usuários em sua [](teams-app-setup-policies.md)organização, você precisa adicionar Walkie Talkie à Política de Configuração de Aplicativo atribuída aos usuários do Centro de   Administração do [Teams.](https://admin.teams.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="b3df5-111">To enable this feature for users in your organization, you need to add Walkie Talkie to the [App Setup Policy](teams-app-setup-policies.md) assigned to users from the [Teams Admin Center](https://admin.teams.microsoft.com/).</span></span>

<span data-ttu-id="b3df5-112">Depois de habilitado, o Walkie Talkie ficará disponível no aplicativo Android dentro de 48 horas.</span><span class="sxs-lookup"><span data-stu-id="b3df5-112">Once enabled, Walkie Talkie will become available on the Android app within 48 hours.</span></span>

### <a name="adding-walkie-talkie-to-your-app-list"></a><span data-ttu-id="b3df5-113">Adicionar Walkie Talkie à sua lista de aplicativos</span><span class="sxs-lookup"><span data-stu-id="b3df5-113">Adding Walkie Talkie to your app list</span></span>

<span data-ttu-id="b3df5-114">No Centro de administração do Microsoft Teams, em políticas de configuração de aplicativos do **Teams,** você deve ter Permitir que o  >   **pinamento do usuário** seja definido como **Em.**</span><span class="sxs-lookup"><span data-stu-id="b3df5-114">In the Microsoft Teams admin center, under **Teams app** > **Setup policies**, you should have **Allow user pinning** set to **On**.</span></span> <span data-ttu-id="b3df5-115">Em seguida, na seção Aplicativos Fixados, clique **em +Adicionar Aplicativos.**</span><span class="sxs-lookup"><span data-stu-id="b3df5-115">Then, under the Pinned Apps section, click **+Add Apps**.</span></span>

:::image type="content" source="media/deploy-walkie-talkie-1.png" alt-text="Mostra a seção Aplicativos Fixados e o botão Adicionar Aplicativos a ser selecionado.":::

<span data-ttu-id="b3df5-117">No painel **Adicionar aplicativos fixados** que  aparece à direita, use a caixa de texto Pesquisar para procurar o Walkie Talkie.</span><span class="sxs-lookup"><span data-stu-id="b3df5-117">On the **Add pinned apps** panel that appears on the right, use the **Search** textbox to look for Walkie Talkie.</span></span> <span data-ttu-id="b3df5-118">Quando você o tiver como resultado de pesquisa, clique no **botão** Adicionar à direita do nome para adicioná-lo à sua lista.</span><span class="sxs-lookup"><span data-stu-id="b3df5-118">When you have it as a search result, click the **Add** button to the right of the name to add it to your list.</span></span>

:::image type="content" source="media/deploy-walkie-talkie-2.png" alt-text="Mostra a barra lateral Adicionar aplicativos fixados com o Walkie inserido no painel de pesquisa e o aplicativo Walkie Talkie nos resultados da pesquisa, com o botão Adicionar ao lado dele.":::

<span data-ttu-id="b3df5-120">O aplicativo Walkie Talkie agora deve aparecer na lista Aplicativos Fixados e estará disponível para uso depois que você clicar no **botão** Salvar.</span><span class="sxs-lookup"><span data-stu-id="b3df5-120">The Walkie Talkie app should now appear on the Pinned Apps list, and be available for use once you click the **Save** button.</span></span>

:::image type="content" source="media/deploy-walkie-talkie-3.png" alt-text="Mostra a lista de aplicativos fixados com o aplicativo Walkie Talkie adicionado e o botão Salvar abaixo da lista.":::

### <a name="network-documentation"></a><span data-ttu-id="b3df5-122">Documentação de rede</span><span class="sxs-lookup"><span data-stu-id="b3df5-122">Network documentation</span></span>

<span data-ttu-id="b3df5-123">O Walkie Talkie no Teams requer conectividade com a Internet e, abaixo das condições de rede, são necessários para uma experiência ideal.</span><span class="sxs-lookup"><span data-stu-id="b3df5-123">Walkie Talkie in Teams requires Internet connectivity and below the network conditions are required for optimal experience.</span></span>

|<span data-ttu-id="b3df5-124">Indicador</span><span class="sxs-lookup"><span data-stu-id="b3df5-124">Metric</span></span> | <span data-ttu-id="b3df5-125">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="b3df5-125">Required</span></span> |
|---|---|
|<span data-ttu-id="b3df5-126">Latência (RTT)</span><span class="sxs-lookup"><span data-stu-id="b3df5-126">Latency (RTT)</span></span> | <span data-ttu-id="b3df5-127">< 300ms</span><span class="sxs-lookup"><span data-stu-id="b3df5-127">< 300ms</span></span> |
|<span data-ttu-id="b3df5-128">Tremulação</span><span class="sxs-lookup"><span data-stu-id="b3df5-128">Jitter</span></span> |<span data-ttu-id="b3df5-129">< 30ms</span><span class="sxs-lookup"><span data-stu-id="b3df5-129">< 30ms</span></span> |
|<span data-ttu-id="b3df5-130">Perda de pacote</span><span class="sxs-lookup"><span data-stu-id="b3df5-130">Packet Loss</span></span> |<span data-ttu-id="b3df5-131">< 1%</span><span class="sxs-lookup"><span data-stu-id="b3df5-131">< 1%</span></span> |

<span data-ttu-id="b3df5-132">Conforme mencionado acima, a qualidade da mídia em tempo real em uma rede IP é muito impactada pela qualidade da conectividade de rede, mas especialmente pela quantidade de:</span><span class="sxs-lookup"><span data-stu-id="b3df5-132">As noted above, the quality of real-time media over an IP network is greatly impacted by the quality of the network connectivity, but especially by the amount of:</span></span>

- <span data-ttu-id="b3df5-133">**Latência** – este é o tempo necessário para obter um pacote IP do ponto A ao ponto B na rede.</span><span class="sxs-lookup"><span data-stu-id="b3df5-133">**Latency** - This is the time it takes to get an IP packet from point A to point B on the network.</span></span> <span data-ttu-id="b3df5-134">Esse atraso de propagação de rede está essencialmente ligado à distância física entre os dois pontos e a velocidade da luz, incluindo a sobrecarga adicional sofrida pelos vários roteadores intermediários.</span><span class="sxs-lookup"><span data-stu-id="b3df5-134">This network propagation delay is essentially tied to physical distance between the two points and the speed of light, including additional overhead taken by the various routers in between.</span></span> <span data-ttu-id="b3df5-135">A latência é medida como RTT (Tempo de Ida e Volta).</span><span class="sxs-lookup"><span data-stu-id="b3df5-135">Latency is measured as Round-trip Time (RTT).</span></span>
- <span data-ttu-id="b3df5-136">**Perda de** pacote – isso geralmente é definido como uma porcentagem de pacotes que são perdidos em um determinado período de tempo.</span><span class="sxs-lookup"><span data-stu-id="b3df5-136">**Packet Loss** - This is often defined as a percentage of packets that are lost in a given window of time.</span></span> <span data-ttu-id="b3df5-137">A perda de pacote afeta diretamente a qualidade do áudio, desde pacotes perdidos pequenos e individuais que quase não têm impacto, até perdas de estouro de retorno para trás que causam corte total do áudio.</span><span class="sxs-lookup"><span data-stu-id="b3df5-137">Packet loss directly affects audio quality—from small, individual lost packets having almost no impact, to back-to-back burst losses that cause complete audio cut-out.</span></span>
- <span data-ttu-id="b3df5-138">**Jitter** - Essa é a alteração média de atraso entre pacotes sucessivos.</span><span class="sxs-lookup"><span data-stu-id="b3df5-138">**Jitter** - This is the average change in delay between successive packets.</span></span>

<span data-ttu-id="b3df5-139">O uso esperado de dados do Walkie Talkie é de cerca de 20KB/s ao enviar ou receber áudio.</span><span class="sxs-lookup"><span data-stu-id="b3df5-139">Expected data usage from Walkie Talkie is around 20KB/s when sending or receiving audio.</span></span> <span data-ttu-id="b3df5-140">Quando ocioso, o uso esperado de dados do Walkie Talkie é negligível.</span><span class="sxs-lookup"><span data-stu-id="b3df5-140">When idle, expected data usage from Walkie Talkie is negligible.</span></span>

### <a name="walkie-talkie-devices"></a><span data-ttu-id="b3df5-141">Dispositivos Walkie Talkie</span><span class="sxs-lookup"><span data-stu-id="b3df5-141">Walkie Talkie devices</span></span>

<span data-ttu-id="b3df5-142">Os trabalhadores da linha de frente geralmente precisam falar e receber chamadas do Walkie Talkie mesmo quando seus telefones estão bloqueados.</span><span class="sxs-lookup"><span data-stu-id="b3df5-142">Frontline workers often need to speak and receive Walkie Talkie calls even when their phones are locked.</span></span> <span data-ttu-id="b3df5-143">Essa experiência é possível por meio de dispositivos especializados com um botão PTT dedicado.</span><span class="sxs-lookup"><span data-stu-id="b3df5-143">This experience is possible through specialized devices with a dedicated PTT button.</span></span>

- <span data-ttu-id="b3df5-144">Auriculares</span><span class="sxs-lookup"><span data-stu-id="b3df5-144">Headsets</span></span>
  - <span data-ttu-id="b3df5-145">Fones de ouvido com fio ([Electronics Electronics)](https://www.kleinelectronics.com/poc-accessories/mtwt/)</span><span class="sxs-lookup"><span data-stu-id="b3df5-145">Wired headsets ([Klein Electronics](https://www.kleinelectronics.com/poc-accessories/mtwt/))</span></span>
  - <span data-ttu-id="b3df5-146">Fones de ouvido sem fio[(Jabra BlueParrott)](https://www.blueparrott.com/microsoft-teams-walkie-talkie)</span><span class="sxs-lookup"><span data-stu-id="b3df5-146">Wireless headsets ([Jabra BlueParrott](https://www.blueparrott.com/microsoft-teams-walkie-talkie))</span></span>
- <span data-ttu-id="b3df5-147">Telefones robustos</span><span class="sxs-lookup"><span data-stu-id="b3df5-147">Rugged phones</span></span>
  - <span data-ttu-id="b3df5-148">Samsung Galaxy XCover Pro</span><span class="sxs-lookup"><span data-stu-id="b3df5-148">Samsung Galaxy XCover Pro</span></span>
    - <span data-ttu-id="b3df5-149">[Mais informações.](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/)</span><span class="sxs-lookup"><span data-stu-id="b3df5-149">[More info](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/).</span></span>
    - <span data-ttu-id="b3df5-150">[Guia de configuração.](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm)</span><span class="sxs-lookup"><span data-stu-id="b3df5-150">[Setup guide](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm).</span></span>

> [!NOTE]
> <span data-ttu-id="b3df5-151">Esses dispositivos não são certificados do Teams.</span><span class="sxs-lookup"><span data-stu-id="b3df5-151">These devices are not Teams certified.</span></span> <span data-ttu-id="b3df5-152">Eles foram validados para trabalhar com o Walkie Talkie do Teams.</span><span class="sxs-lookup"><span data-stu-id="b3df5-152">They have been validated to work with Teams Walkie Talkie.</span></span>

### <a name="license-requirements"></a><span data-ttu-id="b3df5-153">Requisitos de licença</span><span class="sxs-lookup"><span data-stu-id="b3df5-153">License requirements</span></span>

<span data-ttu-id="b3df5-154">O aplicativo Walkie Talkie está incluído em todas as licenças pagas do Teams nas [assinaturas do Office 365.](https://docs.microsoft.com/MicrosoftTeams/office-365-licensing)</span><span class="sxs-lookup"><span data-stu-id="b3df5-154">Walkie Talkie app is included in all paid licenses of Teams in [Office 365 subscriptions](https://docs.microsoft.com/MicrosoftTeams/office-365-licensing).</span></span> <span data-ttu-id="b3df5-155">Para obter mais informações sobre como obter o Teams, confira [Como obter acesso ao Microsoft Teams?](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)</span><span class="sxs-lookup"><span data-stu-id="b3df5-155">For more information about getting Teams, check out [How do I get access to Microsoft Teams](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)?</span></span>

> [!NOTE]
> <span data-ttu-id="b3df5-156">Determinados recursos avançados podem exigir licenciamento adicional.</span><span class="sxs-lookup"><span data-stu-id="b3df5-156">Certain advanced features may require additional licensing.</span></span> <span data-ttu-id="b3df5-157">Por exemplo, a integração com o Samsung Galaxy XCover Pro requer uma licença do Knox.</span><span class="sxs-lookup"><span data-stu-id="b3df5-157">For example, integration with Samsung Galaxy XCover Pro requires a Knox license.</span></span>

## <a name="further-information"></a><span data-ttu-id="b3df5-158">Mais informações</span><span class="sxs-lookup"><span data-stu-id="b3df5-158">Further information</span></span>

- <span data-ttu-id="b3df5-159">O ITAdmins pode manter o controle sobre quem está usando o Walkie Talkie por meio de Políticas de Aplicativos.</span><span class="sxs-lookup"><span data-stu-id="b3df5-159">ITAdmins can maintain control over who is using Walkie Talkie through App Policies.</span></span>
- <span data-ttu-id="b3df5-160">Se o seu trabalhador da linha de frente estiver usando dados móveis para se comunicar por meio do Teams, Walkie Talkie usará o mesmo método.</span><span class="sxs-lookup"><span data-stu-id="b3df5-160">If your Frontline worker is using mobile data to communicate via Teams, Walkie Talkie will use the same method.</span></span>
- <span data-ttu-id="b3df5-161">O Walkie Talkie deve funcionar bem em situações de baixa largura de banda ou situações em que seu smartphone está conectado e funcionando.</span><span class="sxs-lookup"><span data-stu-id="b3df5-161">Walkie Talkie should work well in low bandwidth situations, or situations where your smartphone is connected and working.</span></span> <span data-ttu-id="b3df5-162">Walkie Talkie não funcionará quando não houver conectividade.</span><span class="sxs-lookup"><span data-stu-id="b3df5-162">Walkie Talkie will not work when there is no connectivity at all.</span></span>

<span data-ttu-id="b3df5-163">Para saber mais sobre a experiência do usuário final, consulte:</span><span class="sxs-lookup"><span data-stu-id="b3df5-163">For further reading on the end-user experience, see:</span></span>

- [<span data-ttu-id="b3df5-164">Começar a trabalhar com o Walkie Talkie do Teams</span><span class="sxs-lookup"><span data-stu-id="b3df5-164">Get started with Teams Walkie Talkie</span></span>](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [<span data-ttu-id="b3df5-165">Comunique-se com sua equipe com Walkie Talkie</span><span class="sxs-lookup"><span data-stu-id="b3df5-165">Communicate with your team with Walkie Talkie</span></span>](https://support.microsoft.com/office/communicate-with-your-team-in-walkie-talkie-e4342550-5516-4451-b9ec-93166b60f8a4)
