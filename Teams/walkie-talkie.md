---
title: Aplicativo Walkie Talkie em Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Como configurar o aplicativo Walkie Talkie em Microsoft Teams, de uma perspectiva ITAdmin.
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
ms.openlocfilehash: 9f86d40772eb067a561708c6170ef2354bae521b
ms.sourcegitcommit: 05411575d07d3eadc79d872d1cf81b36aae25621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2021
ms.locfileid: "52479068"
---
# <a name="walkie-talkie-app-in-microsoft-teams"></a><span data-ttu-id="efd05-103">Aplicativo Walkie Talkie em Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="efd05-103">Walkie Talkie app in Microsoft Teams</span></span>

<span data-ttu-id="efd05-104">O aplicativo Walkie Talkie no Teams fornece comunicação instantânea por push-to-talk (PTT) para sua equipe e agora está disponível no Android.</span><span class="sxs-lookup"><span data-stu-id="efd05-104">The Walkie Talkie app in Teams provides instant push-to-talk (PTT) communication for your team and is now available on Android.</span></span> <span data-ttu-id="efd05-105">O Walkie Talkie permite que os usuários se conectem com sua equipe usando os mesmos canais subjacentes de que são membros.</span><span class="sxs-lookup"><span data-stu-id="efd05-105">Walkie Talkie allows users to connect with their team using the same underlying channels they're members of.</span></span> <span data-ttu-id="efd05-106">Somente os usuários que se conectam ao Walkie Talkie em um canal se tornam participantes e podem se comunicar uns com os outros usando o push-to-talk, um de cada vez.</span><span class="sxs-lookup"><span data-stu-id="efd05-106">Only users who connect to Walkie Talkie in a channel become participants and can communicate with each other using push-to-talk, one at a time.</span></span>

<span data-ttu-id="efd05-107">Com o Walkie Talkie no Teams, os funcionários da Linha de Frente agora podem se comunicar com segurança com uma experiência PTT conhecida sem precisar carregar rádios volumosos, e o Walkie Talkie funciona em qualquer lugar com conectividade wi-fi ou internet celular.</span><span class="sxs-lookup"><span data-stu-id="efd05-107">With Walkie Talkie in Teams, Frontline workers can now securely communicate with a familiar PTT experience without needing to carry bulky radios, and Walkie Talkie works anywhere with WiFi or cellular internet connectivity.</span></span>

## <a name="getting-started"></a><span data-ttu-id="efd05-108">Introdução</span><span class="sxs-lookup"><span data-stu-id="efd05-108">Getting started</span></span>

### <a name="deploying-walkie-talkie"></a><span data-ttu-id="efd05-109">Implantando o Walkie Talkie</span><span class="sxs-lookup"><span data-stu-id="efd05-109">Deploying Walkie Talkie</span></span>

<span data-ttu-id="efd05-110">Atualmente, o Walkie Talkie está disponível para dispositivos Android com o Google Serviços Móveis (GMS) e não está pré-instalado.</span><span class="sxs-lookup"><span data-stu-id="efd05-110">Currently, Walkie Talkie is available for Android devices with Google Mobile Services (GMS) and is not pre-installed.</span></span> <span data-ttu-id="efd05-111">Para habilitar esse recurso para usuários em sua organização, [](teams-app-setup-policies.md)você precisa adicionar o Walkie Talkie à Política de Instalação de Aplicativos atribuída aos usuários do Centro de Administração   Teams [.](https://admin.teams.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="efd05-111">To enable this feature for users in your organization, you need to add Walkie Talkie to the [App Setup Policy](teams-app-setup-policies.md) assigned to users from the [Teams Admin Center](https://admin.teams.microsoft.com/).</span></span> <span data-ttu-id="efd05-112">Depois de habilitado, o Walkie Talkie ficará disponível no aplicativo Android dentro de 48 horas.</span><span class="sxs-lookup"><span data-stu-id="efd05-112">Once enabled, Walkie Talkie will become available on the Android app within 48 hours.</span></span>

### <a name="adding-walkie-talkie-to-your-app-list"></a><span data-ttu-id="efd05-113">Adicionando o Walkie Talkie à sua lista de aplicativos</span><span class="sxs-lookup"><span data-stu-id="efd05-113">Adding Walkie Talkie to your app list</span></span>

<span data-ttu-id="efd05-114">No centro de Microsoft Teams de administração, em Teams políticas de Instalação de aplicativos , você deve ter Permitir que o  >   **pinning** do usuário seja **definido** como On .</span><span class="sxs-lookup"><span data-stu-id="efd05-114">In the Microsoft Teams admin center, under **Teams app** > **Setup policies**, you should have **Allow user pinning** set to **On**.</span></span> <span data-ttu-id="efd05-115">Em seguida, na seção Aplicativos Fixados, clique **em +Adicionar Aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="efd05-115">Then, under the Pinned Apps section, click **+Add Apps**.</span></span>

:::image type="content" source="media/deploy-walkie-talkie-1.png" alt-text="Mostra a seção Aplicativos Fixados e o botão Adicionar Aplicativos a ser selecionado.":::

<span data-ttu-id="efd05-117">No painel **Adicionar aplicativos** fixados que  aparece à direita, use a caixa de texto Pesquisar para procurar Walkie Talkie.</span><span class="sxs-lookup"><span data-stu-id="efd05-117">On the **Add pinned apps** panel that appears on the right, use the **Search** textbox to look for Walkie Talkie.</span></span> <span data-ttu-id="efd05-118">Quando você o tiver como resultado de pesquisa, selecione o botão **Adicionar** à direita do nome para adicioná-lo à sua lista.</span><span class="sxs-lookup"><span data-stu-id="efd05-118">When you have it as a search result, select the **Add** button to the right of the name to add it to your list.</span></span>

:::image type="content" source="media/deploy-walkie-talkie-2.png" alt-text="Mostra a barra lateral Adicionar aplicativos fixados com o Walkie inserido no painel de pesquisa e o aplicativo Walkie Talkie nos resultados da pesquisa, com o botão Adicionar ao lado dele.":::

<span data-ttu-id="efd05-120">O aplicativo Walkie Talkie agora deve aparecer na lista Aplicativos Fixados e estar disponível para uso depois de clicar no **botão Salvar.**</span><span class="sxs-lookup"><span data-stu-id="efd05-120">The Walkie Talkie app should now appear on the Pinned Apps list, and be available for use once you click the **Save** button.</span></span>

:::image type="content" source="media/deploy-walkie-talkie-3.png" alt-text="Mostra a lista Aplicativos fixados com o aplicativo Walkie Talkie adicionado e o botão Salvar abaixo da lista.":::

### <a name="network-documentation"></a><span data-ttu-id="efd05-122">Documentação de rede</span><span class="sxs-lookup"><span data-stu-id="efd05-122">Network documentation</span></span>

<span data-ttu-id="efd05-123">O Walkie Talkie no Teams requer conectividade com a Internet e abaixo das condições de rede são necessárias para uma experiência ideal.</span><span class="sxs-lookup"><span data-stu-id="efd05-123">Walkie Talkie in Teams requires Internet connectivity and below the network conditions are required for optimal experience.</span></span>

|<span data-ttu-id="efd05-124">Indicador</span><span class="sxs-lookup"><span data-stu-id="efd05-124">Metric</span></span> | <span data-ttu-id="efd05-125">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="efd05-125">Required</span></span> |
|---|---|
|<span data-ttu-id="efd05-126">Latência (RTT)</span><span class="sxs-lookup"><span data-stu-id="efd05-126">Latency (RTT)</span></span> | <span data-ttu-id="efd05-127">< 300ms</span><span class="sxs-lookup"><span data-stu-id="efd05-127">< 300ms</span></span> |
|<span data-ttu-id="efd05-128">Tremulação</span><span class="sxs-lookup"><span data-stu-id="efd05-128">Jitter</span></span> |<span data-ttu-id="efd05-129">< 30ms</span><span class="sxs-lookup"><span data-stu-id="efd05-129">< 30ms</span></span> |
|<span data-ttu-id="efd05-130">Perda de pacote</span><span class="sxs-lookup"><span data-stu-id="efd05-130">Packet Loss</span></span> |<span data-ttu-id="efd05-131">< 1%</span><span class="sxs-lookup"><span data-stu-id="efd05-131">< 1%</span></span> |

<span data-ttu-id="efd05-132">Conforme mencionado acima, a qualidade da mídia em tempo real em uma rede IP é muito impactada pela qualidade da conectividade de rede, mas especialmente pela quantidade de:</span><span class="sxs-lookup"><span data-stu-id="efd05-132">As noted above, the quality of real-time media over an IP network is greatly impacted by the quality of the network connectivity, but especially by the amount of:</span></span>

- <span data-ttu-id="efd05-133">**Latência** - Esse é o tempo necessário para obter um pacote IP do ponto A para o ponto B na rede.</span><span class="sxs-lookup"><span data-stu-id="efd05-133">**Latency** - This is the time it takes to get an IP packet from point A to point B on the network.</span></span> <span data-ttu-id="efd05-134">Esse atraso de propagação de rede está essencialmente vinculado à distância física entre os dois pontos e a velocidade da luz, incluindo mais sobrecargas tomadas pelos vários roteadores entre eles.</span><span class="sxs-lookup"><span data-stu-id="efd05-134">This network propagation delay is essentially tied to physical distance between the two points and the speed of light, including more overhead taken by the various routers in between.</span></span> <span data-ttu-id="efd05-135">A latência é medida como tempo de ida e volta (RTT).</span><span class="sxs-lookup"><span data-stu-id="efd05-135">Latency is measured as Round-trip Time (RTT).</span></span>
- <span data-ttu-id="efd05-136">**Tremidação entre Chegadas** - Essa é a alteração média de atraso entre pacotes sucessivos.</span><span class="sxs-lookup"><span data-stu-id="efd05-136">**Inter-Arrival Jitter** - This is the average change in delay between successive packets.</span></span>
- <span data-ttu-id="efd05-137">**Perda de** pacotes - Isso geralmente é definido como uma porcentagem de pacotes perdidos em uma determinada janela de tempo.</span><span class="sxs-lookup"><span data-stu-id="efd05-137">**Packet Loss** - This is often defined as a percentage of packets that are lost in a given window of time.</span></span> <span data-ttu-id="efd05-138">A perda de pacotes afeta diretamente a qualidade do áudio, desde pacotes perdidos pequenos e individuais que quase não têm impacto, até perdas de estouro de back-to-back que causam o corte total do áudio.</span><span class="sxs-lookup"><span data-stu-id="efd05-138">Packet loss directly affects audio quality—from small, individual lost packets having almost no impact, to back-to-back burst losses that cause complete audio cut-out.</span></span>

<span data-ttu-id="efd05-139">O uso esperado de dados do Walkie Talkie é de cerca de 20 Kb/s ao enviar ou receber áudio.</span><span class="sxs-lookup"><span data-stu-id="efd05-139">Expected data usage from Walkie Talkie is around 20 Kb/s when sending or receiving audio.</span></span> <span data-ttu-id="efd05-140">Quando ocioso, o uso esperado de dados do Walkie Talkie é insignificante.</span><span class="sxs-lookup"><span data-stu-id="efd05-140">When idle, expected data usage from Walkie Talkie is negligible.</span></span>

### <a name="walkie-talkie-devices"></a><span data-ttu-id="efd05-141">Dispositivos Walkie Talkie</span><span class="sxs-lookup"><span data-stu-id="efd05-141">Walkie Talkie devices</span></span>

<span data-ttu-id="efd05-142">Os funcionários de linha de frente geralmente precisam falar e receber chamadas do Walkie Talkie mesmo quando seus telefones estão bloqueados.</span><span class="sxs-lookup"><span data-stu-id="efd05-142">Frontline workers often need to speak and receive Walkie Talkie calls even when their phones are locked.</span></span> <span data-ttu-id="efd05-143">Essa experiência é possível por meio de dispositivos especializados com um botão PTT dedicado.</span><span class="sxs-lookup"><span data-stu-id="efd05-143">This experience is possible through specialized devices with a dedicated PTT button.</span></span>

- <span data-ttu-id="efd05-144">**Headsets**</span><span class="sxs-lookup"><span data-stu-id="efd05-144">**Headsets**</span></span>
  - <span data-ttu-id="efd05-145">Fones de ouvido sem fio</span><span class="sxs-lookup"><span data-stu-id="efd05-145">Wireless headsets</span></span> 
    - [<span data-ttu-id="efd05-146">BlueParrott</span><span class="sxs-lookup"><span data-stu-id="efd05-146">BlueParrott</span></span>](https://www.blueparrott.com/microsoft-teams-walkie-talkie)
  - <span data-ttu-id="efd05-147">Fones de ouvido com fio</span><span class="sxs-lookup"><span data-stu-id="efd05-147">Wired headsets</span></span> 
    - [<span data-ttu-id="efd05-148">Eletrônica de Klein</span><span class="sxs-lookup"><span data-stu-id="efd05-148">Klein Electronics</span></span>](https://www.kleinelectronics.com/poc-accessories/mtwt/)
- <span data-ttu-id="efd05-149">**Telefones robustos**</span><span class="sxs-lookup"><span data-stu-id="efd05-149">**Rugged phones**</span></span>
  - <span data-ttu-id="efd05-150">Samsung [Galaxy XCover Pro](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/), [Galaxy XCover 5](https://www.samsung.com/de/smartphones/others/galaxy-xcover-5-black-64gb-sm-g525fzkdeeb/buy), [Guia do Galaxy Active 3](https://www.samsung.com/us/business/tablets/galaxy-tab-active/buy/)</span><span class="sxs-lookup"><span data-stu-id="efd05-150">Samsung [Galaxy XCover Pro](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/), [Galaxy XCover 5](https://www.samsung.com/de/smartphones/others/galaxy-xcover-5-black-64gb-sm-g525fzkdeeb/buy), [Galaxy Tab Active 3](https://www.samsung.com/us/business/tablets/galaxy-tab-active/buy/)</span></span>
    -  <span data-ttu-id="efd05-151">Configuração manual - Com Teams instalado, navegue até Configurações > Recursos Avançados > XCover/Chave Ativa.</span><span class="sxs-lookup"><span data-stu-id="efd05-151">Manual setup - With Teams installed, navigate to Settings > Advanced Features > XCover/Active key.</span></span> <span data-ttu-id="efd05-152">Aciona a tecla 'Controlar XCover com aplicativo' e selecione 'Teams'</span><span class="sxs-lookup"><span data-stu-id="efd05-152">Turn on 'Control XCover key with app' and select 'Teams'</span></span>
    -  [<span data-ttu-id="efd05-153">Instalação do MDM</span><span class="sxs-lookup"><span data-stu-id="efd05-153">MDM setup</span></span>](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm)

> [!NOTE]
> <span data-ttu-id="efd05-154">Esses dispositivos não são Teams certificados.</span><span class="sxs-lookup"><span data-stu-id="efd05-154">These devices are not Teams certified.</span></span> <span data-ttu-id="efd05-155">Eles foram validados para trabalhar com Teams Walkie Talkie.</span><span class="sxs-lookup"><span data-stu-id="efd05-155">They have been validated to work with Teams Walkie Talkie.</span></span>

### <a name="license-requirements"></a><span data-ttu-id="efd05-156">Requisitos de licença</span><span class="sxs-lookup"><span data-stu-id="efd05-156">License requirements</span></span>

<span data-ttu-id="efd05-157">O aplicativo Walkie Talkie está incluído em todas as licenças pagas de Teams em [Office 365 assinaturas](/office365/servicedescriptions/teams-service-description).</span><span class="sxs-lookup"><span data-stu-id="efd05-157">Walkie Talkie app is included in all paid licenses of Teams in [Office 365 subscriptions](/office365/servicedescriptions/teams-service-description).</span></span> <span data-ttu-id="efd05-158">Para obter mais informações sobre Teams, confira [Como obter acesso a Microsoft Teams?](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)</span><span class="sxs-lookup"><span data-stu-id="efd05-158">For more information about getting Teams, check out [How do I get access to Microsoft Teams](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)?</span></span>

> [!NOTE]
> <span data-ttu-id="efd05-159">Determinados recursos avançados podem exigir licenciamento adicional.</span><span class="sxs-lookup"><span data-stu-id="efd05-159">Certain advanced features may require additional licensing.</span></span> <span data-ttu-id="efd05-160">Por exemplo, a integração com o Samsung Galaxy XCover Pro requer uma licença do Knox.</span><span class="sxs-lookup"><span data-stu-id="efd05-160">For example, integration with Samsung Galaxy XCover Pro requires a Knox license.</span></span>

## <a name="further-information"></a><span data-ttu-id="efd05-161">Mais informações</span><span class="sxs-lookup"><span data-stu-id="efd05-161">Further information</span></span>

- <span data-ttu-id="efd05-162">ITAdmins pode manter o controle sobre quem está usando o Walkie Talkie por meio de Políticas de Aplicativos.</span><span class="sxs-lookup"><span data-stu-id="efd05-162">ITAdmins can maintain control over who is using Walkie Talkie through App Policies.</span></span>
- <span data-ttu-id="efd05-163">Se o seu funcionário da Linha de Frente estiver usando dados móveis para se comunicar Teams, o Walkie Talkie usará o mesmo método.</span><span class="sxs-lookup"><span data-stu-id="efd05-163">If your Frontline worker is using mobile data to communicate via Teams, Walkie Talkie will use the same method.</span></span>
- <span data-ttu-id="efd05-164">O Walkie Talkie deve funcionar bem em situações de baixa largura de banda ou situações em que seu smartphone está conectado e funcionando.</span><span class="sxs-lookup"><span data-stu-id="efd05-164">Walkie Talkie should work well in low bandwidth situations, or situations where your smartphone is connected and working.</span></span> <span data-ttu-id="efd05-165">Walkie Talkie não funcionará quando não houver conectividade.</span><span class="sxs-lookup"><span data-stu-id="efd05-165">Walkie Talkie will not work when there is no connectivity at all.</span></span>

<span data-ttu-id="efd05-166">Para saber mais sobre a experiência do usuário final, consulte:</span><span class="sxs-lookup"><span data-stu-id="efd05-166">For further reading on the end-user experience, see:</span></span>

- [<span data-ttu-id="efd05-167">Começar a Teams Walkie Talkie</span><span class="sxs-lookup"><span data-stu-id="efd05-167">Get started with Teams Walkie Talkie</span></span>](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [<span data-ttu-id="efd05-168">Comunicar-se com sua equipe com o Walkie Talkie</span><span class="sxs-lookup"><span data-stu-id="efd05-168">Communicate with your team with Walkie Talkie</span></span>](https://support.microsoft.com/office/communicate-with-your-team-in-walkie-talkie-e4342550-5516-4451-b9ec-93166b60f8a4)
