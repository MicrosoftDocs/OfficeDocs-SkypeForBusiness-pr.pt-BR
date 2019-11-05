---
title: Verificar sua conexão com a Internet
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
localization_priority: Priority
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: ''
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4dbfd1bdaec48ebe8c6adbed86da431a6f4ecbfc
ms.sourcegitcommit: 30b4b979e20066253e32ab9e44d79c48a97e6211
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/05/2019
ms.locfileid: "37972272"
---
# <a name="check-your-internet-connection"></a><span data-ttu-id="74c44-102">Verificar sua conexão com a Internet</span><span class="sxs-lookup"><span data-stu-id="74c44-102">Check your Internet connection</span></span>

<span data-ttu-id="74c44-103">O Business Voice está localizado na nuvem do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="74c44-103">Business Voice is located in the cloud with Microsoft 365.</span></span> <span data-ttu-id="74c44-104">Todo computador e dispositivo que usa o Microsoft Teams e o Business Voice precisa de uma conexão com a Internet.</span><span class="sxs-lookup"><span data-stu-id="74c44-104">Every computer and device that uses Microsoft Teams and Business Voice needs a connection to the Internet.</span></span> <span data-ttu-id="74c44-105">Para obter a melhor experiência com o Business Voice, é preciso uma conexão de Internet de banda larga que suporte o número esperado de chamadas telefônicas que serão feitas a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="74c44-105">To get the best experience with Business Voice, you need a broadband Internet connection that can support the expected number of phone calls that will be made at any one time.</span></span> <span data-ttu-id="74c44-106">Também é preciso ter certeza de que os computadores da sua rede podem acessar os servidores do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="74c44-106">You also need to make sure that computers on your network can reach Microsoft 365 servers.</span></span>

<span data-ttu-id="74c44-107">Para seguir estas etapas, você precisa ter um locatário com uma das seguintes assinaturas:</span><span class="sxs-lookup"><span data-stu-id="74c44-107">To follow these steps, you need to have a tenant with one of the following subscriptions:</span></span>

* <span data-ttu-id="74c44-108">Office 365 Business Essentials</span><span class="sxs-lookup"><span data-stu-id="74c44-108">Office 365 Business Essentials</span></span>
* <span data-ttu-id="74c44-109">Office 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="74c44-109">Office 365 Business Premium</span></span>
* <span data-ttu-id="74c44-110">Office 365 E1</span><span class="sxs-lookup"><span data-stu-id="74c44-110">Office 365 Enterprise E1</span></span>
* <span data-ttu-id="74c44-111">Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="74c44-111">Office 365 Enterprise E3</span></span>
* <span data-ttu-id="74c44-112">Office 365 F1</span><span class="sxs-lookup"><span data-stu-id="74c44-112">Office 365 Enterprise F1</span></span>
* <span data-ttu-id="74c44-113">Microsoft 365 A1</span><span class="sxs-lookup"><span data-stu-id="74c44-113">Microsoft 365 A1</span></span>
* <span data-ttu-id="74c44-114">Microsoft 365 A3</span><span class="sxs-lookup"><span data-stu-id="74c44-114">Microsoft 365 A3</span></span>
* <span data-ttu-id="74c44-115">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="74c44-115">Microsoft 365 E3</span></span>
* <span data-ttu-id="74c44-116">Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="74c44-116">Microsoft 365 Business</span></span>

<span data-ttu-id="74c44-117">Você não precisa de uma licença do Business Voice para seguir estas etapas.</span><span class="sxs-lookup"><span data-stu-id="74c44-117">You don't need a Business Voice license to follow these steps.</span></span>

## <a name="check-your-internet-connection-speed"></a><span data-ttu-id="74c44-118">Verifique a velocidade da sua conexão com a Internet</span><span class="sxs-lookup"><span data-stu-id="74c44-118">Check your Internet connection speed</span></span>

<span data-ttu-id="74c44-119">Este artigo ajuda a determinar se a conexão com a Internet é rápida o suficiente para o número de pessoas que precisam fazer chamadas telefônicas, hospedar videoconferências e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="74c44-119">This article helps you determine whether your Internet connection is fast enough for the number of people who need to make phone calls, host video conferences, and so on.</span></span> <span data-ttu-id="74c44-120">Você inserirá algumas informações sobre a organização e receberá um relatório com o quanto da sua conexão com a Internet será usada pelo Teams e Business Voice.</span><span class="sxs-lookup"><span data-stu-id="74c44-120">You'll enter some information about your organization and get back a report with how much of your Internet connection will be used by Teams and Business Voice.</span></span>

### <a name="get-information-about-your-internet-connection-and-users"></a><span data-ttu-id="74c44-121">Obter informações sobre a conexão com a Internet e os usuários</span><span class="sxs-lookup"><span data-stu-id="74c44-121">Get information about your Internet connection and users</span></span>

<span data-ttu-id="74c44-122">Antes de começar, você precisa saber as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="74c44-122">Before you start, you need to know the following information:</span></span>

* <span data-ttu-id="74c44-123">A velocidade da sua conexão com a Internet.</span><span class="sxs-lookup"><span data-stu-id="74c44-123">The speed of your Internet connection.</span></span>
* <span data-ttu-id="74c44-124">Quantas pessoas usarão o Business Voice basicamente do seu escritório.</span><span class="sxs-lookup"><span data-stu-id="74c44-124">How many people will use Business Voice mainly from your office.</span></span>
* <span data-ttu-id="74c44-125">Quantas pessoas usarão o Business Voice basicamente de um local remoto, como um escritório residencial.</span><span class="sxs-lookup"><span data-stu-id="74c44-125">How many people will use Business Voice mainly from a remote location, such as a home office.</span></span>

### <a name="enter-your-information-into-the-network-planner"></a><span data-ttu-id="74c44-126">Inserir suas informações no planejador de rede</span><span class="sxs-lookup"><span data-stu-id="74c44-126">Enter your information into the network planner</span></span>

<span data-ttu-id="74c44-127">Veja aqui o que você precisa fazer:</span><span class="sxs-lookup"><span data-stu-id="74c44-127">Here's what you need to do:</span></span>

1. <span data-ttu-id="74c44-128">Abra um navegador e vá para https://admin.teams.microsoft.com, e entre com uma conta que tenha permissões de Administrador Global.</span><span class="sxs-lookup"><span data-stu-id="74c44-128">Open a browser and go to https://admin.teams.microsoft.com and sign in with an account that has Global Administrator permissions.</span></span> <span data-ttu-id="74c44-129">A conta que você usou para se inscrever no Office 365 tem essas permissões.</span><span class="sxs-lookup"><span data-stu-id="74c44-129">The account you used to sign up for Office 365 has these permissions.</span></span>
1. <span data-ttu-id="74c44-130">Abra **Configurações em toda a organização** e selecione **Planejador de rede**.</span><span class="sxs-lookup"><span data-stu-id="74c44-130">Open **Org-wide settings** and then select **Network planner**.</span></span>
1. <span data-ttu-id="74c44-131">Em **Planos de rede**, selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="74c44-131">Under **Network plans**, select **Add**.</span></span> <span data-ttu-id="74c44-132">Dê um nome ao seu plano e selecione **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="74c44-132">Give your plan a name, and then select **Apply**.</span></span> <span data-ttu-id="74c44-133">Seu plano de rede deve ter a seguinte aparência:</span><span class="sxs-lookup"><span data-stu-id="74c44-133">Your network plan should look like this:</span></span>

    ![Tela principal do Planejador de rede](../media/network-planner-main.png)
1. <span data-ttu-id="74c44-135">Clique no nome do seu plano de rede (**Escritório principal** na imagem acima).</span><span class="sxs-lookup"><span data-stu-id="74c44-135">Click on your network plan's name (**Main office** in the picture above).</span></span>
1. <span data-ttu-id="74c44-136">Na próxima página, selecione **Adicionar um site de rede** na guia **Sites de rede**.</span><span class="sxs-lookup"><span data-stu-id="74c44-136">On the next page, select **Add a network site** under the **Network sites** tab.</span></span>
1. <span data-ttu-id="74c44-137">Preencha as seguintes informações e, em seguida, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="74c44-137">Fill out the following information and then select **Save**.</span></span>

    ![Informações do site do planejador de rede](../media/network-planner-site-info.png)
1. <span data-ttu-id="74c44-139">Na guia **Relatório**, selecione **Iniciar um relatório**.</span><span class="sxs-lookup"><span data-stu-id="74c44-139">Under the **Report** tab, select **Start a report**.</span></span>
1. <span data-ttu-id="74c44-140">Preencha as seguintes informações e, em seguida, selecione **Gerar relatório**.</span><span class="sxs-lookup"><span data-stu-id="74c44-140">Fill out the following information and then select **Generate report**</span></span>

    ![Informações do relatório do planejador de rede](../media/network-planner-report-info.png)

### <a name="find-your-minimum-internet-connection-speed"></a><span data-ttu-id="74c44-142">Encontre sua velocidade mínima de conexão com a Internet</span><span class="sxs-lookup"><span data-stu-id="74c44-142">Find your minimum Internet connection speed</span></span>

<span data-ttu-id="74c44-143">Ao selecionar **Gerar relatório**, o Office 365 cria um relatório parecido com este:</span><span class="sxs-lookup"><span data-stu-id="74c44-143">When you select **Generate report**, Office 365 creates a report that looks like this:</span></span>

![Detalhes do relatório do planejador de rede](../media/network-planner-report.png)

<span data-ttu-id="74c44-145">O número realçado mostra o quanto da sua conexão com a Internet será usada pelo Teams e Business Voice.</span><span class="sxs-lookup"><span data-stu-id="74c44-145">The highlighted number shows how much of your Internet connection Teams and Business Voice will use.</span></span> <span data-ttu-id="74c44-146">Recomendamos que esse número não ultrapasse 30% da velocidade total da conexão com a Internet.</span><span class="sxs-lookup"><span data-stu-id="74c44-146">We recommend that this number be no more than 30% of your total Internet connection speed.</span></span> <span data-ttu-id="74c44-147">Por exemplo, se a conexão com a Internet for 60 Mbps, O Teams e o Business Voice deverão ocupar no máximo 18 Mbps.</span><span class="sxs-lookup"><span data-stu-id="74c44-147">For example, if your Internet connection is 60Mbps, Teams and Business Voice should take up no more than 18Mbps.</span></span>

<span data-ttu-id="74c44-148">Você pode encontrar a sua velocidade mínima de conexão com a Internet fazendo este cálculo: `<highlighted number> / .3`.</span><span class="sxs-lookup"><span data-stu-id="74c44-148">You can find your minimum Internet connection speed by doing this calculation: `<highlighted number> / .3`.</span></span> <span data-ttu-id="74c44-149">Usando o número realçado na figura acima, o cálculo seria `4.6875 / .3 = 15.6`.</span><span class="sxs-lookup"><span data-stu-id="74c44-149">Using the highlighted number in the picture above, the calculation would be `4.6875 / .3 = 15.6`.</span></span> <span data-ttu-id="74c44-150">Isso significa que a velocidade mínima de conexão com a Internet precisa ser de pelo menos 15,6 Mbps.</span><span class="sxs-lookup"><span data-stu-id="74c44-150">This means your minimum Internet connection speed needs to be at least 15.6Mbps.</span></span>

<span data-ttu-id="74c44-151">Se o Teams e o Business Voice usarem mais de 30% da velocidade total da conexão com a Internet, o número realçado será mostrado em vermelho.</span><span class="sxs-lookup"><span data-stu-id="74c44-151">If Teams and Business Voice will use more than 30% of your total Internet connection speed, the highlighted number will show up as red.</span></span> <span data-ttu-id="74c44-152">Se isso acontecer, talvez seja necessário atualizar sua conexão com a Internet.</span><span class="sxs-lookup"><span data-stu-id="74c44-152">If this happens, you might need to upgrade your Internet connection.</span></span>

![Aviso de velocidade de conexão](../media/network-planner-report-speed-warning.png)

## <a name="make-sure-computers-and-devices-on-your-network-can-reach-microsoft-365"></a><span data-ttu-id="74c44-154">Verifique se os computadores e dispositivos da rede podem acessar o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="74c44-154">Make sure computers and devices on your network can reach Microsoft 365</span></span>

<span data-ttu-id="74c44-155">Para funcionar corretamente, os computadores e dispositivos que você deseja usar com o Business Voice precisam se comunicar com os servidores Microsoft 365 usando portas de rede específicas.</span><span class="sxs-lookup"><span data-stu-id="74c44-155">To work correctly, computers and devices you want to use with Business Voice need to communicate with Microsoft 365 servers using specific network ports.</span></span> <span data-ttu-id="74c44-156">As portas de rede são essencialmente portas pelas quais computadores e dispositivos podem se comunicar por meio de uma rede ou da Internet.</span><span class="sxs-lookup"><span data-stu-id="74c44-156">Network ports are essentially doors through which computers and devices can talk to each other over a network or the Internet.</span></span> <span data-ttu-id="74c44-157">O firewall deve permitir que computadores e dispositivos na rede acessem o Microsoft 365 usando as seguintes portas de rede de saída:</span><span class="sxs-lookup"><span data-stu-id="74c44-157">Your firewall needs to allow computers and devices on your network to reach Microsoft 365 using the following outbound network ports:</span></span>

* <span data-ttu-id="74c44-158">**Portas TCP** 80 e 443</span><span class="sxs-lookup"><span data-stu-id="74c44-158">TCP ports 80 and 443 outgoing from clients that will use Teams</span></span>
* <span data-ttu-id="74c44-159">**Portas UDP** 3478, 3479, 3480 e 3481</span><span class="sxs-lookup"><span data-stu-id="74c44-159">**UDP ports** 3478, 3479, 3480, and 3481</span></span>

<span data-ttu-id="74c44-160">A maneira mais fácil de verificar se o firewall permite a comunicação nas portas de rede é fazer uma chamada de teste usando o Teams.</span><span class="sxs-lookup"><span data-stu-id="74c44-160">The easiest way to check whether your firewall allows communication on these network ports is to make a test call using Teams.</span></span> <span data-ttu-id="74c44-161">Para fazer uma chamada de teste, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="74c44-161">To make a test call, do the following:</span></span>

1. <span data-ttu-id="74c44-162">Vá para https://aka.ms/getteams em um computador na rede para instalar o Teams.</span><span class="sxs-lookup"><span data-stu-id="74c44-162">Go to https://aka.ms/getteams on a computer on your network to install Teams.</span></span> <span data-ttu-id="74c44-163">Verifique se os alto-falantes e um microfone estão conectados ao computador.</span><span class="sxs-lookup"><span data-stu-id="74c44-163">Make sure speakers and a microphone are connected to this computer.</span></span>
2. <span data-ttu-id="74c44-164">Abra o Teams e entre usando uma conta do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="74c44-164">Open Teams and sign in using a Microsoft 365 account</span></span>
3. <span data-ttu-id="74c44-165">No Teams, selecione sua foto do perfil e, em seguida, **Configurações** > **Dispositivos**</span><span class="sxs-lookup"><span data-stu-id="74c44-165">In Teams, select your profile picture, then **Settings** > **Devices**</span></span>
4. <span data-ttu-id="74c44-166">Escolha **Faça uma chamada de teste** em **Dispositivos de áudio**</span><span class="sxs-lookup"><span data-stu-id="74c44-166">Choose **Make a test call** under **Audio devices**</span></span>
5. <span data-ttu-id="74c44-167">Siga os avisos para deixar uma mensagem e reproduzi-la para você </span><span class="sxs-lookup"><span data-stu-id="74c44-167">Follow the prompts to leave a message and have it played back to you</span></span>

* <span data-ttu-id="74c44-168">Se a chamada for conectada e você conseguir ouvir a sua mensagem, seu firewall está configurado corretamente.</span><span class="sxs-lookup"><span data-stu-id="74c44-168">If the call connects and you can hear your message played back to you, your firewall is set up correctly.</span></span>
* <span data-ttu-id="74c44-169">Se a chamada for conectada, mas você não conseguir ouvir os avisos ou a sua mensagem, verifique se os alto-falantes e o microfone estão configurados corretamente e detectados pelo computador.</span><span class="sxs-lookup"><span data-stu-id="74c44-169">If the call connects but you can't hear the prompts or your message played back to you, make sure your speakers and microphone are set up correctly and detected by the computer.</span></span> <span data-ttu-id="74c44-170">Tente novamente.</span><span class="sxs-lookup"><span data-stu-id="74c44-170">Try again.</span></span>
* <span data-ttu-id="74c44-171">Se a chamada não se conectar ou se você não conseguir ouvir a sua mensagem, talvez seja necessário atualizar o firewall para permitir as portas de rede listadas acima.</span><span class="sxs-lookup"><span data-stu-id="74c44-171">If the call doesn't connect or if it does but you can't hear your message played back to you, you might need to update your firewall to allow the network ports listed above.</span></span> <span data-ttu-id="74c44-172">Verifique a documentação do firewall sobre como permitir que as portas de rede acessem a Internet ou entre em contato com um especialista de TI para ajudá-lo.</span><span class="sxs-lookup"><span data-stu-id="74c44-172">Check your firewall's documentation on how to allow network ports to reach the Internet, or contact an IT specialist to help you.</span></span>

<span data-ttu-id="74c44-173">Se você é um profissional de TI e deseja obter mais informações sobre como preparar redes maiores ou mais complexas para dar suporte ao Business Voice, dê uma olhada em [Avaliar meu ambiente](../3-envision-evaluate-my-environment.md).</span><span class="sxs-lookup"><span data-stu-id="74c44-173">If you're an IT professional and want more information about how to prepare larger or more complex networks to support Business Voice, take a look at [Evaluate my environment](../3-envision-evaluate-my-environment.md).</span></span> <span data-ttu-id="74c44-174">O artigo[Avaliar meu ambiente](../3-envision-evaluate-my-environment.md) fornece informações adicionais sobre requisitos de largura de banda, proxy e firewall e também como testar sua rede usando a [Ferramenta de Avaliação de Rede](../3-envision-evaluate-my-environment.md#test-the-network).</span><span class="sxs-lookup"><span data-stu-id="74c44-174">The [Evaluate my environment](../3-envision-evaluate-my-environment.md) article gives additional information about bandwidth, proxy, and firewall requirements and also how to test your network using the [Network Assessment Tool](../3-envision-evaluate-my-environment.md#test-the-network).</span></span>
