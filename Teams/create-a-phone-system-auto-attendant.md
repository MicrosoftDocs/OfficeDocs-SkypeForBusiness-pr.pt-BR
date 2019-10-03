---
title: Configurar um atendedor automático do Cloud
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: waseemh
ms.topic: article
ms.assetid: 6fc2687c-0abf-43b8-aa54-7c3b2a84b67c
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Saiba como configurar e testar atendedores automáticos da nuvem para o Microsoft Teams.
ms.openlocfilehash: 0cac6b1bb7d19e91e4042bcb0673f6c677e77d2e
ms.sourcegitcommit: 2d31209aae9e0171693389db97b0b5c974864673
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2019
ms.locfileid: "37375704"
---
# <a name="set-up-a-cloud-auto-attendant"></a><span data-ttu-id="248b2-103">Configurar um atendedor automático do Cloud</span><span class="sxs-lookup"><span data-stu-id="248b2-103">Set up a Cloud auto attendant</span></span>

<span data-ttu-id="248b2-104">Os atendedores automáticos permitem que as pessoas liguem para sua organização e naveguem em um sistema de menus para obter o departamento certo, a fila de chamadas, a pessoa ou a operadora.</span><span class="sxs-lookup"><span data-stu-id="248b2-104">Auto attendants let people that call in to your organization and navigate a menu system to get them to the right department, call queue, person, or the operator.</span></span> <span data-ttu-id="248b2-105">Você pode criar um atendedor automático para sua organização usando o centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="248b2-105">You can create an auto attendant for your organization by using the Microsoft Teams admin center.</span></span> <span data-ttu-id="248b2-106">Para criar um novo atendedor automático, vá para **voz** no painel de navegação esquerdo e, em seguida, selecione **atendedores** > automáticos**Adicionar novo**.</span><span class="sxs-lookup"><span data-stu-id="248b2-106">To create a new auto attendant, go to **Voice** in the left navigation, and then select **Auto attendants** > **Add new**.</span></span>

<span data-ttu-id="248b2-107">Se você quiser saber mais sobre atendedores automáticos, consulte [o que são atendedores automáticos da nuvem?](/microsoftteams/what-are-phone-system-auto-attendants)</span><span class="sxs-lookup"><span data-stu-id="248b2-107">If you want to learn more about auto attendants, see [What are Cloud auto attendants?](/microsoftteams/what-are-phone-system-auto-attendants)</span></span>

> [!NOTE]
> <span data-ttu-id="248b2-108">Este artigo se aplica ao Microsoft Teams e ao Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="248b2-108">This article applies to both Microsoft Teams and Skype for Business Online.</span></span>

## <a name="step-1--get-started"></a><span data-ttu-id="248b2-109">Etapa 1-Introdução</span><span class="sxs-lookup"><span data-stu-id="248b2-109">Step 1 — Get started</span></span>

- <span data-ttu-id="248b2-110">Um atendedor automático é necessário para ter uma conta de recurso associada.</span><span class="sxs-lookup"><span data-stu-id="248b2-110">An auto attendant is required to have an associated resource account.</span></span> <span data-ttu-id="248b2-111">Consulte [gerenciar contas de recursos no Teams](manage-resource-accounts.md) para obter detalhes sobre contas de recursos e todas as licenças necessárias.</span><span class="sxs-lookup"><span data-stu-id="248b2-111">See [Manage resource accounts in Teams](manage-resource-accounts.md) for details on resource accounts and all licenses required.</span></span>

> [!TIP]
> <span data-ttu-id="248b2-112">Para redirecionar chamadas para um operador ou uma opção de menu que seja um usuário online com uma licença do **sistema de telefonia** , será necessário habilitá-las para o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="248b2-112">To redirect calls to an operator or a menu option that is an Online user with a **Phone System** license, you will need to enable them for Enterprise Voice.</span></span> <span data-ttu-id="248b2-113">Consulte [atribuir licenças do Skype for Business](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) ou [atribuir licenças do Microsoft Teams](assign-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="248b2-113">See [Assign Skype for Business licenses](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) or [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="248b2-114">Você também pode usar o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="248b2-114">You can also use Windows PowerShell.</span></span> <span data-ttu-id="248b2-115">Por exemplo, execute:`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="248b2-115">For example, run: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

## <a name="step-2--create-a-new-auto-attendant"></a><span data-ttu-id="248b2-116">Etapa 2 — criar um novo atendedor automático</span><span class="sxs-lookup"><span data-stu-id="248b2-116">Step 2 — Create a new auto attendant</span></span>

> [!IMPORTANT]
> <span data-ttu-id="248b2-117">Cada atendedor automático é necessário para ter uma [conta de recurso](manage-resource-accounts.md)associada.</span><span class="sxs-lookup"><span data-stu-id="248b2-117">Every auto attendant is required to have an associated [resource account](manage-resource-accounts.md).</span></span> <span data-ttu-id="248b2-118">Você deve criar a conta do recurso primeiro, então você pode associá-la ao atendedor automático.</span><span class="sxs-lookup"><span data-stu-id="248b2-118">You must create the resource account first, then you can associate it to the auto attendant.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="248b2-119">Usar o centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="248b2-119">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="248b2-120">No **centro de administração do Microsoft Teams**, clique em**atendedores automáticos**de **voz** > e, em seguida, clique em **+ novo**:</span><span class="sxs-lookup"><span data-stu-id="248b2-120">In the **Microsoft Teams admin center**, click   **Voice** > **Auto attendants**, then click **+ New**:</span></span>

#### <a name="general-info-page"></a><span data-ttu-id="248b2-121">Página de informações gerais</span><span class="sxs-lookup"><span data-stu-id="248b2-121">General info page</span></span>

![Captura de tela da página meu atendedor automático](media/edacec94-9384-4a87-be0a-5c49a151287e.png)

* * *

![Ícone do número 1, fazendo referência a um texto explicativo na captura de tela anterior](media/sfbcallout1.png)

<span data-ttu-id="248b2-124">**Nome** Digite um nome de exibição descritivo para o atendedor automático.</span><span class="sxs-lookup"><span data-stu-id="248b2-124">**Name** Enter a descriptive display name for your auto attendant.</span></span> <span data-ttu-id="248b2-125">O nome é obrigatório e pode conter até 64 caracteres, incluindo espaços.</span><span class="sxs-lookup"><span data-stu-id="248b2-125">The name is required and can contain up to 64 characters, including spaces.</span></span> <span data-ttu-id="248b2-126">Ela está listada na coluna **nome** na guia **atendedores automáticos** .</span><span class="sxs-lookup"><span data-stu-id="248b2-126">It is listed in the **Name** column on the **Auto attendants** tab.</span></span>

* * *

![Ícone do número 2, fazendo referência a um texto explicativo na captura de tela anterior](media/sfbcallout2.png)

<span data-ttu-id="248b2-128"><a name="phonenumber"> </a></span><span class="sxs-lookup"><span data-stu-id="248b2-128"></span></span>

<span data-ttu-id="248b2-129">**Conta do recurso** Clique neste botão para selecionar uma ou mais contas de recursos para se conectar ao seu novo atendedor automático.</span><span class="sxs-lookup"><span data-stu-id="248b2-129">**Resource account** Click this button to select one or more resource accounts to connect to your new auto attendant.</span></span> <span data-ttu-id="248b2-130">Todos os atendedores automáticos devem ter uma conta de recurso associada.</span><span class="sxs-lookup"><span data-stu-id="248b2-130">All auto attendants are required to have an associated resource account.</span></span> <span data-ttu-id="248b2-131">Uma conta de recurso pode ter um número de telefone associado à conta, mas um número de telefone não é um requisito.</span><span class="sxs-lookup"><span data-stu-id="248b2-131">A resource account can have a phone number associated to the account, but a phone number isn't a requirement.</span></span> <span data-ttu-id="248b2-132">Um atendedor automático de nível superior geralmente tem uma conta de recurso com um número de telefone atribuído, mas o atendedor automático aninhado (usado como um menu de nível 2 ao qual o atendedor automático de primeiro nível se conecta) pode não ter um número de telefone atribuído à sua conta de recurso.</span><span class="sxs-lookup"><span data-stu-id="248b2-132">A top-level auto attendant usually has a resource account with an assigned phone number, but nested auto attendant (used as a level 2 menu that the first-level auto attendant connects to) might not have a phone number assigned to its resource account.</span></span>

* * *

<span data-ttu-id="248b2-133">![Ícone do número 3, fazendo referência a um texto explicativo na](media/sfbcallout3.png)
 <a name="timezone"> </a> captura de tela anterior</span><span class="sxs-lookup"><span data-stu-id="248b2-133">![Icon of the number 3, referencing a callout in the previous screenshot](media/sfbcallout3.png)
<a name="timezone"> </a></span></span>

<span data-ttu-id="248b2-134">**Fuso horário** Você deve definir o fuso horário para o atendedor automático, mas ele não precisa corresponder ao fuso horário do endereço principal de sua organização.</span><span class="sxs-lookup"><span data-stu-id="248b2-134">**Time zone** You must set the time zone for your auto attendant, but it doesn't need to correspond to the time zone of the main address listed for your organization.</span></span> <span data-ttu-id="248b2-135">Cada atendedor automático pode ter um fuso horário diferente, e o horário comercial definido para o atendedor automático é definido com base no fuso horário selecionado aqui.</span><span class="sxs-lookup"><span data-stu-id="248b2-135">Each auto attendant can have a different time zone, and the business hours set for the auto attendant are set based on the time zone that you select here.</span></span>

* * *

![Ícone do número 4, fazendo referência a um texto explicativo na captura de tela anterior](media/sfbcallout4.png)

<span data-ttu-id="248b2-137"><a name="language"> </a></span><span class="sxs-lookup"><span data-stu-id="248b2-137"></span></span>

<span data-ttu-id="248b2-138">**Idioma** Selecione o idioma que você deseja usar para o atendedor automático entre os idiomas disponíveis listados.</span><span class="sxs-lookup"><span data-stu-id="248b2-138">**Language** Select the language that you want to use for your auto attendant from any of the available languages listed.</span></span> <span data-ttu-id="248b2-139">O idioma que você define aqui é o idioma que o atendedor automático usa para interagir com as pessoas que fazem chamadas para este atendedor automático e todos os prompts do sistema são reproduzidos nesse idioma.</span><span class="sxs-lookup"><span data-stu-id="248b2-139">The language you set here is the language that the auto attendant uses to interact with people that call in to this auto attendant, and all the system prompts are played in this language.</span></span>

* * *

![Ícone do número 5, fazendo referência a um texto explicativo na captura de tela anterior](media/sfbcallout5.png)

<span data-ttu-id="248b2-141"><a name="operator"> </a></span><span class="sxs-lookup"><span data-stu-id="248b2-141"></span></span>

<span data-ttu-id="248b2-142">**Operador** de Isso é opcional, mas você pode definir a opção de **operador** para permitir que os chamadores se quebrem dos menus e falar com uma pessoa.</span><span class="sxs-lookup"><span data-stu-id="248b2-142">**Operator** This is optional, but you can set the **Operator** option to allow callers to break out of the menus and speak to a person.</span></span>

<span data-ttu-id="248b2-143">A tecla 0 é atribuída ao operador por padrão.</span><span class="sxs-lookup"><span data-stu-id="248b2-143">The 0 key is assigned to Operator by default.</span></span>

<span data-ttu-id="248b2-144">Se você definir um operador, também precisará dizer às pessoas que chamam a opção sobre a opção nas **Opções do menu Editar** na página de **manipulação de chamadas do horário comercial** .</span><span class="sxs-lookup"><span data-stu-id="248b2-144">If you set an Operator, you will also need to tell people who call about the option in the **Edit menu options** on the **Business hours call handling** page.</span></span> <span data-ttu-id="248b2-145">Se você definir um operador em seu atendedor automático, será necessário inserir o texto de aviso correspondente na caixa os **chamadores ouvirá** ou alterar seu arquivo de áudio para incluir essa opção.</span><span class="sxs-lookup"><span data-stu-id="248b2-145">If you set an operator on your auto attendant, you need to enter the corresponding prompt text in the **Callers will hear** box or change your audio file to include this option.</span></span> <span data-ttu-id="248b2-146">Por exemplo, "Para falar com o operador, pressione 0".</span><span class="sxs-lookup"><span data-stu-id="248b2-146">For example, "For the Operator, press zero."</span></span>

<span data-ttu-id="248b2-147">Você tem várias maneiras de definir o operador:</span><span class="sxs-lookup"><span data-stu-id="248b2-147">You have several ways to set the Operator:</span></span>

- <span data-ttu-id="248b2-148">**Pessoa da sua empresa** com uma licença de **Sistema de Telefonia** habilitada para Enterprise Voice ou com Planos de Chamadas do Office 365 atribuídos.</span><span class="sxs-lookup"><span data-stu-id="248b2-148">**Person in your company** with a **Phone System** license that is enabled for Enterprise Voice or assigned Calling Plans in Office 365.</span></span>

     > [!Note]
     > <span data-ttu-id="248b2-149">A **Pessoa da sua empresa** pode ser um usuário Online ou um usuário hospedado no local usando o Skype for Business Server 2015 ou o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="248b2-149">**Person in your company** can be an Online user or a user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013.</span></span>

- <span data-ttu-id="248b2-150">**Aplicativo de voz** Selecione o nome de uma conta de recurso associada a uma fila de chamadas ou atendedor automático que já foi criado.</span><span class="sxs-lookup"><span data-stu-id="248b2-150">**Voice application** Select the name of a resource account associated to either a call queue or auto attendant that has already been created.</span></span>
- <span data-ttu-id="248b2-151">Você pode configurá-lo para que a pessoa que faz a chamada seja enviada para o correio de voz.</span><span class="sxs-lookup"><span data-stu-id="248b2-151">You can set it up so the person calling is sent to voicemail.</span></span> <span data-ttu-id="248b2-152">Para fazer isso, selecione **pessoa em sua empresa** e defina as chamadas desta pessoa para serem encaminhadas diretamente para o correio de voz.</span><span class="sxs-lookup"><span data-stu-id="248b2-152">To do this, select **Person in your company** and set this person's calls to be forwarded directly to voicemail.</span></span>

* * *

![Ícone do número 6, fazendo referência a um texto explicativo na captura de tela anterior](media/sfbcallout6.png)

<span data-ttu-id="248b2-154">**Habilitar entradas de voz** O reconhecimento de fala estará disponível se esta opção for selecionada.</span><span class="sxs-lookup"><span data-stu-id="248b2-154">**Enable voice inputs** Speech recognition is available if this option is selected.</span></span> <span data-ttu-id="248b2-155">As pessoas que chamam podem usar entrada de voz no [idioma que você definiu](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="248b2-155">People that call in can use voice input in the  [language you set](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span></span> <span data-ttu-id="248b2-156">Se quiser permitir que as pessoas usem o teclado de telefone, você pode desativar o reconhecimento de fala definindo-a como desativada.</span><span class="sxs-lookup"><span data-stu-id="248b2-156">If you want to only let people use their phone keypad, you can disable speech recognition by setting it to off.</span></span>

* * *

<span data-ttu-id="248b2-157">Quando terminar de selecionar as opções, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="248b2-157">When you are finished with your selections, click **Next**.</span></span>

#### <a name="business-hours-page"></a><span data-ttu-id="248b2-158">Página de horário comercial</span><span class="sxs-lookup"><span data-stu-id="248b2-158">Business hours page</span></span>

<span data-ttu-id="248b2-159">Por padrão, o horário comercial é definido como 9:00 de até 5:00 PM, de segunda a sexta-feira.</span><span class="sxs-lookup"><span data-stu-id="248b2-159">By default, business hours are set to 9:00 am to 5:00 pm, Monday through Friday.</span></span> <span data-ttu-id="248b2-160">Todas as horas que não estão incluídas no horário comercial são consideradas após o horário comercial.</span><span class="sxs-lookup"><span data-stu-id="248b2-160">All hours that aren't included in business hours are considered after business hours.</span></span> <span data-ttu-id="248b2-161">Você pode clicar em **selecionar 24/7** para fazer todas as horas de trabalho.</span><span class="sxs-lookup"><span data-stu-id="248b2-161">You can click **Select 24/7** to make all hours business hours.</span></span> <span data-ttu-id="248b2-162">A menos que você selecione a opção **selecionar 24/7** , a página de **configurações de chamada de horas** extras será usada para configurar as regras de tratamento de chamadas para o horário comercial do atendedor automático.</span><span class="sxs-lookup"><span data-stu-id="248b2-162">Unless you select the **Select 24/7** option, the **After hours call settings** page will be used to configure the call handling rules for after business hours for the auto attendant.</span></span>

![Captura de tela da página de horário comercial](media/61769547-cdb4-45c0-af5a-3d6e0731fbc6.png)

* * *

![Ícone do número 1, fazendo referência a um texto explicativo na captura de tela anterior](media/sfbcallout1.png)

<span data-ttu-id="248b2-165">Por padrão, o horário comercial é definido como de segunda a sexta-feira, 9:00 am-5:00 PM.</span><span class="sxs-lookup"><span data-stu-id="248b2-165">By default, business hours are set to Monday to Friday, 9:00 am-5:00 pm.</span></span> <span data-ttu-id="248b2-166">Selecione a opção **limpar todas as horas** para desmarcar todas as horas no cronograma.</span><span class="sxs-lookup"><span data-stu-id="248b2-166">Select **Clear all hours** option to unselect all hours in the schedule.</span></span> <span data-ttu-id="248b2-167">Quando você seleciona **Redefinir para padrão**, o horário comercial é redefinido para segunda a sexta-feira, 9:00 am-5:00 PM.</span><span class="sxs-lookup"><span data-stu-id="248b2-167">When you select **Reset to default**, business hours are reset to Monday to Friday, 9:00 am-5:00 pm.</span></span>

* * *

![Ícone do número 2, fazendo referência a um texto explicativo na captura de tela anterior](media/sfbcallout2.png)

<span data-ttu-id="248b2-169">Para alterar o horário comercial, realce o horário comercial que você deseja definir no calendário.</span><span class="sxs-lookup"><span data-stu-id="248b2-169">To change business hours, highlight the business hours you want to set in the calendar.</span></span> <span data-ttu-id="248b2-170">O calendário permite que você selecione horários comerciais em intervalos de 30 minutos, e o horário comercial selecionado aqui é baseado no fuso horário que você definiu na página **informações gerais** .</span><span class="sxs-lookup"><span data-stu-id="248b2-170">The calendar allows you to select business hours in 30-minute intervals, and the business hours you select here are based on the time zone that you set on the **General info** page.</span></span> <span data-ttu-id="248b2-171">Para configurar um intervalo (horário de almoço, por exemplo), desmarque ou arraste para desmarcar o horário no calendário.</span><span class="sxs-lookup"><span data-stu-id="248b2-171">To set up a break (a lunch break, for example), deselect or drag to deselect the time on the calendar.</span></span> <span data-ttu-id="248b2-172">Você pode definir várias quebras dentro do horário comercial.</span><span class="sxs-lookup"><span data-stu-id="248b2-172">You can set multiple breaks within business hours.</span></span>

* * *

<span data-ttu-id="248b2-173">Quando terminar de selecionar as opções, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="248b2-173">When you are finished with your selections, click **Next**.</span></span>

#### <a name="business-hours-call-settings"></a><span data-ttu-id="248b2-174">Configurações de chamada para horário comercial</span><span class="sxs-lookup"><span data-stu-id="248b2-174">Business hours call settings</span></span>

> [!TIP]
> <span data-ttu-id="248b2-175">Se você usar um cronograma personalizado de horário de trabalho, também precisará configurar o recurso de chamada para após o horário comercial usando a página de **processamento de chamadas de horas** extras, que lhe dará as mesmas opções que **as configurações de chamada do horário comercial**.</span><span class="sxs-lookup"><span data-stu-id="248b2-175">If you use a custom business hours schedule, you will also need to set up call handing for after business hours using the **After hours call handling** page, which will give you the same options as **Business hours call settings**.</span></span>

<span data-ttu-id="248b2-176">Você pode configurar saudações, avisos e menus que as pessoas ouvirão quando ligarem para o número de telefone vinculado ao atendedor automático da sua organização durante o horário comercial.</span><span class="sxs-lookup"><span data-stu-id="248b2-176">You can set up greetings, prompts, and menus that people hear when they call to the phone number linked to your organization's auto attendant during business hours.</span></span>

<span data-ttu-id="248b2-177">![Captura de tela da seção](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)
![de ação da página de manipulação de chamadas para horário comercial da seção ações da página de manipulação de chamadas de horário comercial](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8b.png)</span><span class="sxs-lookup"><span data-stu-id="248b2-177">![Screenshot of the Business hours call handling page Greeting section](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)
![Screenshot of the Business hours call handling page Actions section](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8b.png)</span></span>

* * *

![Ícone do número 1, fazendo referência a um texto explicativo na captura de tela anterior](media/sfbcallout1.png)

<span data-ttu-id="248b2-179"><a name="greetingsandrouting"> </a></span><span class="sxs-lookup"><span data-stu-id="248b2-179"></span></span>

<span data-ttu-id="248b2-180">**Saudação** Uma saudação na hora da empresa é opcional e pode ser definida como **sem saudação**.</span><span class="sxs-lookup"><span data-stu-id="248b2-180">**Greeting** A business hours greeting is optional and can be set to **No greeting**.</span></span> <span data-ttu-id="248b2-181">Nesse caso, o chamador não ouvirá uma mensagem ou saudação antes que a chamada seja manipulada por uma das ações que você selecionar.</span><span class="sxs-lookup"><span data-stu-id="248b2-181">In this case, the caller won't hear a message or greeting before the call is handled by one of the actions you select.</span></span> <span data-ttu-id="248b2-182">Você também pode carregar um arquivo de áudio (em formatos .wav, .mp3 ou. wma) ou criar uma saudação personalizada usando conversão de texto em fala.</span><span class="sxs-lookup"><span data-stu-id="248b2-182">You can also upload an audio file (in .wav, mp3 or .wma formats), or create a custom greeting using Text-to-Speech.</span></span>
- <span data-ttu-id="248b2-183">**Carregar um arquivo de áudio** Se você escolher isso, grave a saudação e, em seguida, carregue seu arquivo de áudio (nos formatos. wav,. mp3 ou. WMA).</span><span class="sxs-lookup"><span data-stu-id="248b2-183">**Upload an audio file** If you choose this, record the greeting and then upload your audio file (in a .wav, .mp3 or .wma format).</span></span>
- <span data-ttu-id="248b2-184">**Digite uma mensagem de saudação** Se você escolher essa opção, insira o texto que deseja que o sistema Leia (até 1000 caracteres).</span><span class="sxs-lookup"><span data-stu-id="248b2-184">**Type a greeting message** If you choose this option, enter the text you want the system to read (up to 1000 characters).</span></span> <span data-ttu-id="248b2-185">Por exemplo, você pode inserir "Bem-vindo à Contoso.</span><span class="sxs-lookup"><span data-stu-id="248b2-185">For example, you might enter "Welcome to Contoso.</span></span> <span data-ttu-id="248b2-186">A sua ligação é muito importante para nós."</span><span class="sxs-lookup"><span data-stu-id="248b2-186">Your call is important to us."</span></span> <span data-ttu-id="248b2-187">na caixa **Os chamadores ouvirão**.</span><span class="sxs-lookup"><span data-stu-id="248b2-187">in the **Callers will hear** box.</span></span>

* * *

![Ícone do número 2, fazendo referência a um texto explicativo na captura de tela anterior](media/sfbcallout2.png)

<span data-ttu-id="248b2-189">Você pode selecionar o que acontece com as chamadas que chegam durante o horário comercial.</span><span class="sxs-lookup"><span data-stu-id="248b2-189">You can select what happens to calls that arrive during business hours.</span></span> <span data-ttu-id="248b2-190">Você pode escolher entre as seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="248b2-190">You can chose from the following actions:</span></span>

<span data-ttu-id="248b2-191"><a name="redirectcalls"> </a></span><span class="sxs-lookup"><span data-stu-id="248b2-191"></span></span>

- <span data-ttu-id="248b2-192">**Desconectar** Se você selecioná-lo, a pessoa que está ligando será desconectada depois de ouvir uma saudação de horário comercial.</span><span class="sxs-lookup"><span data-stu-id="248b2-192">**Disconnect** If you select it, the person calling in will be disconnected after hearing a business hours greeting.</span></span>
- <span data-ttu-id="248b2-193">**Redirecionar chamada** Isso pode ser usado para enviar a chamada automaticamente para:</span><span class="sxs-lookup"><span data-stu-id="248b2-193">**Redirect call** This can be used to automatically send the call to:</span></span>
  - <span data-ttu-id="248b2-194">**Pessoa na empresa** com uma licença de **sistema telefônico** habilitada para Enterprise Voice ou planos de chamada atribuídos no Office 365.</span><span class="sxs-lookup"><span data-stu-id="248b2-194">**Person in company** with a **Phone System** license that is enabled for Enterprise Voice or assigned Calling Plans in Office 365.</span></span> <span data-ttu-id="248b2-195">Você pode configurá-lo para que o chamador possa ser enviado para a caixa postal.</span><span class="sxs-lookup"><span data-stu-id="248b2-195">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="248b2-196">Para fazer isso, selecione **pessoa na empresa** e defina esta pessoa para que as chamadas sejam encaminhadas diretamente para o correio de voz.</span><span class="sxs-lookup"><span data-stu-id="248b2-196">To do this, select **Person in company** and set this person to have their calls forwarded directly to voicemail.</span></span>

    > [!Note]
    > <span data-ttu-id="248b2-197">A **pessoa na empresa** pode ser um usuário online ou um usuário hospedado no local usando o Skype for Business Server 2015 ou o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="248b2-197">**Person in company** can be an Online user or a user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013.</span></span>

   - <span data-ttu-id="248b2-198">Outro **atendedor automático**</span><span class="sxs-lookup"><span data-stu-id="248b2-198">Another **Auto attendant**</span></span>

   <span data-ttu-id="248b2-199">Você pode usar um atendedor automático existente para criar um segundo nível de opções de menu contendo um submenu.</span><span class="sxs-lookup"><span data-stu-id="248b2-199">You can use an existing auto attendant to create a second level of menu options containing a sub-menu.</span></span> <span data-ttu-id="248b2-200">These are called nested auto attendants.</span><span class="sxs-lookup"><span data-stu-id="248b2-200">These are called nested auto attendants.</span></span> <span data-ttu-id="248b2-201">Para enviar a chamada para um atendedor automático aninhado, selecione **pessoa na empresa** e atribua uma conta de recurso, uma que já tenha um atendedor automático associado ou que você associe a um atendedor automático quando terminar de criar este atendedor automático.</span><span class="sxs-lookup"><span data-stu-id="248b2-201">To send the call to a nested auto attendant, select **Person in company** and assign a resource account, either one that already has an associated auto attendant or one that you will associate to an auto attendant once you are done creating this auto attendant.</span></span>

- <span data-ttu-id="248b2-202">**As opções do menu reproduzir** também podem ser usadas para permitir que você configure uma solicitação que você deseja que seja reproduzida.</span><span class="sxs-lookup"><span data-stu-id="248b2-202">**Play menu options** can also be used to let you set up a prompt you want played.</span></span>

* * *

![Ícone do número 3, fazendo referência a um texto explicativo na captura de tela anterior](media/sfbcallout3.png)

<span data-ttu-id="248b2-204">**Prompt do menu** Para criar o prompt do menu principal, você pode usar a conversão de texto em fala ou carregar um arquivo de áudio (.wav, .mp3 ou .wma).</span><span class="sxs-lookup"><span data-stu-id="248b2-204">**Menu prompt** To create main menu prompt, you can either use Text-to-Speech or upload an audio file (.wav, .mp3 or .wma).</span></span> <span data-ttu-id="248b2-205">Você pode digitar o prompt na caixa **definir a navegação no menu para chamadores** ou gravar um arquivo de áudio e dizer, por exemplo: "para vendas, digamos ou pressionar ou dizer 1.</span><span class="sxs-lookup"><span data-stu-id="248b2-205">You can type the prompt in the **Set your menu navigation for callers** box or record an audio file and say, for example: "For Sales, say or press or say 1.</span></span> <span data-ttu-id="248b2-206">Para Serviços, pressione ou fale 2.</span><span class="sxs-lookup"><span data-stu-id="248b2-206">For Services, press or say 2.</span></span> <span data-ttu-id="248b2-207">Para Suporte ao Cliente, pressione ou fale 3.</span><span class="sxs-lookup"><span data-stu-id="248b2-207">For Customer Support, press or say 3.</span></span> <span data-ttu-id="248b2-208">Para falar com o operador, pressione ou fale 0.</span><span class="sxs-lookup"><span data-stu-id="248b2-208">For the operator, press or say 0.</span></span> <span data-ttu-id="248b2-209">Para ouvir este menu novamente, pressione a tecla de asterisco ou fale repetir".</span><span class="sxs-lookup"><span data-stu-id="248b2-209">To hear this menu again, press the star key or say repeat."</span></span> <span data-ttu-id="248b2-210">**Digite uma mensagem de saudação** Se você escolheu isso, insira o texto que deseja que o sistema Leia (até 1000 caracteres).</span><span class="sxs-lookup"><span data-stu-id="248b2-210">**Type a greeting message** If you chose this, you should enter the text you want the system to read (up to 1000 characters).</span></span> <span data-ttu-id="248b2-211">**Carregar um arquivo de áudio** Se você escolher isso, deverá gravar a saudação e depois carregar o arquivo de áudio (nos formatos .wav, .mp3 ou .wma).</span><span class="sxs-lookup"><span data-stu-id="248b2-211">**Upload an audio file** If you chose this, you will need to record the greeting and then upload your audio file (in a .wav, mp3 or .wma format).</span></span>

* * *

![Ícone do número 4, fazendo referência a um texto explicativo na captura de tela anterior](media/sfbcallout4.png)

<span data-ttu-id="248b2-213">**Configuração de opções de menu** As opções de menu usando os botões de tecla no teclado numérico podem ser adicionadas ou removidas.</span><span class="sxs-lookup"><span data-stu-id="248b2-213">**Menu options setup** Menu options using key buttons on the keypad can be added or removed.</span></span> <span data-ttu-id="248b2-214">Para adicionar uma opção de menu, pressione **+ atribuir uma tecla de discagem**.</span><span class="sxs-lookup"><span data-stu-id="248b2-214">To add a menu option, press **+ Assign a dial key**.</span></span> <span data-ttu-id="248b2-215">Uma linha de opções correspondente aparecerá abaixo.</span><span class="sxs-lookup"><span data-stu-id="248b2-215">A corresponding row of options will appear below.</span></span> <span data-ttu-id="248b2-216">Para excluir uma opção de menu, basta clicar à esquerda da tecla correspondente no controle do teclado e clicar no ícone de exclusão acima.</span><span class="sxs-lookup"><span data-stu-id="248b2-216">To delete a menu option, simply click to the left of the corresponding key on the keypad control and click on the delete icon above.</span></span> <span data-ttu-id="248b2-217">A linha de mapeamento de teclas será removida.</span><span class="sxs-lookup"><span data-stu-id="248b2-217">The key mapping row will be removed.</span></span>

> [!TIP]
> <span data-ttu-id="248b2-218">Você terá que atualizar os prompts de menu para o texto ou regravar o áudio separadamente ao adicionar às opções de remoção porque ele não será feito automaticamente para o prompt de menu existente.</span><span class="sxs-lookup"><span data-stu-id="248b2-218">You will have to update menu prompts text or re-record the audio separately when adding to removing options because it won't be automatically done for the existing menu prompt.</span></span>  
>
><span data-ttu-id="248b2-219">Qualquer opção de menu pode ser adicionada e removida em qualquer ordem, e os mapeamentos de chave não precisam ser contínuos.</span><span class="sxs-lookup"><span data-stu-id="248b2-219">Any menu option can be added and removed in any order, and the key mappings don't have to be continuous.</span></span> <span data-ttu-id="248b2-220">É possível, por exemplo, criar um menu com as teclas 0, 1 e 3 mapeadas para as opções, enquanto a tecla 2 não é usada.</span><span class="sxs-lookup"><span data-stu-id="248b2-220">It is possible, for example, to create a menu with keys 0, 1, and 3 mapped to options, while the key 2 isn't used.</span></span>

> [!NOTE]
> <span data-ttu-id="248b2-221">As chaves \* (repetir) e \# (verso) são reservadas pelo sistema e não podem ser reatribuídas.</span><span class="sxs-lookup"><span data-stu-id="248b2-221">The keys \* (Repeat) and \# (Back) are reserved by the system and can't be reassigned.</span></span> <span data-ttu-id="248b2-222">Se o reconhecimento de fala estiver habilitado, pressionar \* corresponderá com "repetir" e # corresponderá com os comandos de voz "verso".</span><span class="sxs-lookup"><span data-stu-id="248b2-222">If speech recognition is enabled, pressing \* will correspond with "Repeat" and # will correspond with the "Back" voice commands.</span></span>

<span data-ttu-id="248b2-223">Para configurar as opções de menu, depois de selecionar as teclas de discagem, será necessário:</span><span class="sxs-lookup"><span data-stu-id="248b2-223">To set up your menu options, after you select the dial key(s), you will need to:</span></span>

- <span data-ttu-id="248b2-224">Digite o **comando de voz** da opção.</span><span class="sxs-lookup"><span data-stu-id="248b2-224">Enter the **Voice command**  of the option.</span></span> <span data-ttu-id="248b2-225">Pode ter até 64 caracteres de comprimento e pode conter várias palavras como "atendimento ao cliente" ou "operações e aterramento".</span><span class="sxs-lookup"><span data-stu-id="248b2-225">This can be up to 64 characters long, and can contain multiple words like "Customer Service" or "Operations and Grounds."</span></span> <span data-ttu-id="248b2-226">Se o reconhecimento de fala estiver habilitado, o nome será reconhecido automaticamente e a pessoa que está ligando poderá pressionar 3, diga "três" ou diga "atendimento ao cliente" para selecionar a opção mapeada para a tecla 3.</span><span class="sxs-lookup"><span data-stu-id="248b2-226">If speech recognition is enabled, the name will automatically be recognized, and the person calling in will be able to either press 3, say "three," or say "Customer Service" to select the option mapped to key 3.</span></span>
- <span data-ttu-id="248b2-227">Selecione o local em que a chamada será enviada se a tecla correspondente for pressionada ou a opção for selecionada usando o reconhecimento de fala.</span><span class="sxs-lookup"><span data-stu-id="248b2-227">Select where the call is to be sent if the corresponding key is pressed, or the option is selected using speech recognition.</span></span> <span data-ttu-id="248b2-228">A chamada pode ser enviada para:</span><span class="sxs-lookup"><span data-stu-id="248b2-228">The call can be sent to:</span></span>

  - <span data-ttu-id="248b2-229">**Operador** de Se o operador já estiver configurado, ele será automaticamente mapeado para a chave 0, mas também pode ser excluído ou reatribuído a uma chave diferente.</span><span class="sxs-lookup"><span data-stu-id="248b2-229">**Operator** If operator is already set up, it is automatically mapped to key 0, but it can also be deleted or reassigned to a different key.</span></span> <span data-ttu-id="248b2-230">If operator isn't set to any key, then the voice command "Operator" will be disabled too.</span><span class="sxs-lookup"><span data-stu-id="248b2-230">If operator isn't set to any key, then the voice command "Operator" will be disabled too.</span></span>
  - <span data-ttu-id="248b2-231">Uma **Pessoa da sua empresa** com uma licença de **Sistema de Telefonia** habilitada para Enterprise Voice ou com um Plano de Chamadas do Office 365 atribuído.</span><span class="sxs-lookup"><span data-stu-id="248b2-231">A **Person in your company** with a **Phone System** license that is enabled for Enterprise Voice or assigned an Calling Plan in Office 365.</span></span> <span data-ttu-id="248b2-232">Você pode configurá-lo para que o chamador possa ser enviado para a caixa postal.</span><span class="sxs-lookup"><span data-stu-id="248b2-232">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="248b2-233">Para fazer isso, selecione **pessoa em sua empresa** e defina esta pessoa para que as chamadas sejam encaminhadas diretamente para o correio de voz.</span><span class="sxs-lookup"><span data-stu-id="248b2-233">To do this, select **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span>

    > [!Note]
    > <span data-ttu-id="248b2-234">**A pessoa em sua empresa** pode ser um usuário online ou um usuário hospedado no local usando o Skype for Business Server ou o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="248b2-234">**Person in your company** can be an Online user or a user hosted on-premises using Skype for Business Server or Lync Server 2013.</span></span>

  - <span data-ttu-id="248b2-235">Outro **atendedor automático**</span><span class="sxs-lookup"><span data-stu-id="248b2-235">Another **Auto attendant**</span></span>

       <span data-ttu-id="248b2-236">Você pode usar um atendedor automático existente para criar um segundo nível de opções de menu contendo um submenu.</span><span class="sxs-lookup"><span data-stu-id="248b2-236">You can use an existing auto attendant to create a second level of menu options containing a sub-menu.</span></span> <span data-ttu-id="248b2-237">These are called nested auto attendants.</span><span class="sxs-lookup"><span data-stu-id="248b2-237">These are called nested auto attendants.</span></span> <span data-ttu-id="248b2-238">Para enviar a chamada para um atendedor automático aninhado, selecione **pessoa na empresa** e atribua uma conta de recurso, uma que já tenha um atendedor automático associado ou que você associe a um atendedor automático quando terminar de criar este atendedor automático.</span><span class="sxs-lookup"><span data-stu-id="248b2-238">To send the call to a nested auto attendant, select **Person in company** and assign a resource account, either one that already has an associated auto attendant or one that you will associate to an auto attendant once you are done creating this auto attendant.</span></span>

        > [!Note]
        > The **Business Hours** of nested (or second-level) auto attendants will also be used, including for the calls sent from other auto attendants that have been set up.

    - <span data-ttu-id="248b2-239">**Aplicativo de voz** Selecione o nome de uma conta de recurso associada a uma fila de chamadas ou atendedor automático que já foi criado.</span><span class="sxs-lookup"><span data-stu-id="248b2-239">**Voice application** Select the name of a resource account associated to either a call queue or auto attendant that has already been created.</span></span>

* * *

![Ícone do número 5, fazendo referência a um texto explicativo na captura de tela anterior](media/sfbcallout5.png)

<span data-ttu-id="248b2-241">**Discar por nome** Se você escolher essa opção, as pessoas que ligarem para pesquisarem pessoas em sua organização serão habilitadas para a pesquisa de pastas usando a pesquisa de diretório.</span><span class="sxs-lookup"><span data-stu-id="248b2-241">**Dial by name** If you choose this option, this will enable people who call in to search for people in your organization using Directory Search.</span></span> <span data-ttu-id="248b2-242">Você pode selecionar as pessoas que serão listadas como disponíveis ou indisponíveis para Discagem por Nome na página **Escopo de discagem**.</span><span class="sxs-lookup"><span data-stu-id="248b2-242">You can select which people will be listed as available or not available for Dial by Name by setting up those options on the **Dial scope** page.</span></span> <span data-ttu-id="248b2-243">Qualquer usuário online com uma licença de **sistema telefônico** ou qualquer usuário hospedado no local usando o Skype for Business Server ou o Lync Server 2013 pode ser encontrado com a discagem por nome.</span><span class="sxs-lookup"><span data-stu-id="248b2-243">Any online user with a **Phone System** license, or any user hosted on-premises using Skype for Business Server or Lync Server 2013, can be found with Dial by Name.</span></span>

* * *

<span data-ttu-id="248b2-244">Quando terminar de selecionar as opções, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="248b2-244">When you are finished with your selections, click on **Next**.</span></span>

#### <a name="holiday-call-settings"></a><span data-ttu-id="248b2-245">Configurações de chamadas de Natal</span><span class="sxs-lookup"><span data-stu-id="248b2-245">Holiday call settings</span></span>

<span data-ttu-id="248b2-246"><a name="holidaygreetings"> </a></span><span class="sxs-lookup"><span data-stu-id="248b2-246"></span></span>

<span data-ttu-id="248b2-247">Você pode adicionar até 20 feriados agendados para cada atendedor automático.</span><span class="sxs-lookup"><span data-stu-id="248b2-247">You can add up to 20 scheduled holidays to each auto attendant.</span></span>

> [!TIP]
> <span data-ttu-id="248b2-248">Você pode ir à tela em**feriados** de **configurações** > de toda a organização para criar feriados ou pode criá-las como parte da criação de um novo manipulador de chamadas.</span><span class="sxs-lookup"><span data-stu-id="248b2-248">You can go the the screen at **Org-wide settings** > **Holidays** to create Holidays, or you can create them as part of creating a new call handler.</span></span>

![Captura de tela da página de configurações de chamadas de Natal](media/50a5ce88-7f39-4210-808a-da7ced969854.png)

![Ícone do número 1, fazendo referência a um texto explicativo na captura de tela anterior](media/sfbcallout1.png)

<span data-ttu-id="248b2-251">Se você já tiver criado outros atendedores automáticos, talvez veja uma opção que pode ser usada ou editada no que você precisa na lista.</span><span class="sxs-lookup"><span data-stu-id="248b2-251">If you've already created other auto attendants, you might see an option you can use or edit into what you need on this list.</span></span> <span data-ttu-id="248b2-252">Caso contrário, você precisará criar um novo manipulador de chamadas.</span><span class="sxs-lookup"><span data-stu-id="248b2-252">If not, you'll need to create a new call handler.</span></span>

<span data-ttu-id="248b2-253">Para adicionar um novo manipulador de chamadas, clique em **+ novo manipulador de chamadas**.</span><span class="sxs-lookup"><span data-stu-id="248b2-253">To add a new call handler, click on **+ New call handler**.</span></span>

* * *

![Captura de tela mostrando a adição de um novo manipulador de chamada](media/50a5ce88-7f39-4210-808a-da7ced969854b.png)

![Ícone do número 1, fazendo referência a um texto explicativo na captura de tela anterior](media/sfbcallout1.png)

<span data-ttu-id="248b2-256">Na nova janela, insira um nome para seu novo manipulador de chamadas na parte superior da tela.</span><span class="sxs-lookup"><span data-stu-id="248b2-256">In the new window, enter a name for your new Call  handler at the top of the screen.</span></span>

![Ícone do número 2, fazendo referência a um texto explicativo na captura de tela anterior](media/sfbcallout2.png)

<span data-ttu-id="248b2-258">Se o nome do seu feriado já existir na lista suspensa de **feriados** , você poderá usá-lo.</span><span class="sxs-lookup"><span data-stu-id="248b2-258">If the name of your holiday already exists in the **Holiday** pull-down list, you can use it.</span></span> <span data-ttu-id="248b2-259">Se o nome do feriado que você precisa ainda não existir, selecione **criar novo feriado** na lista suspensa e atribua um nome e uma data para o novo feriado na nova tela exibida.</span><span class="sxs-lookup"><span data-stu-id="248b2-259">If the holiday name you need does not already exist, select **Create new holiday** in the pull-down list and assign a name and a date for the new holiday in the new screen that appears.</span></span> <span data-ttu-id="248b2-260">Clique em **salvar** quando estiver pronto.</span><span class="sxs-lookup"><span data-stu-id="248b2-260">Click on **Save** when ready.</span></span>

<span data-ttu-id="248b2-261">Os nomes de feriados podem ter até 64 caracteres e devem ser únicos para o mesmo atendedor automático.</span><span class="sxs-lookup"><span data-stu-id="248b2-261">Holiday names may consist of up to 64 characters and must be unique for the same auto attendant.</span></span> <span data-ttu-id="248b2-262">Por exemplo, você não pode ter dois feriados com o nome "Ação de Graças" no mesmo atendedor automático.</span><span class="sxs-lookup"><span data-stu-id="248b2-262">For example, you cannot have two holidays named "Thanksgiving" in the same auto attendant.</span></span>

![Ícone do número 3, fazendo referência a um texto explicativo na captura de tela anterior](media/sfbcallout3.png)

<span data-ttu-id="248b2-264">**Saudação** A saudação é opcional e pode ser definida como **sem saudação**.</span><span class="sxs-lookup"><span data-stu-id="248b2-264">**Greeting** The greeting is optional and can be set to **No greeting**.</span></span> <span data-ttu-id="248b2-265">Nesse caso, a pessoa que liga não ouvirá nenhuma mensagem ou saudação antes da chamada ser atendida por uma das opções selecionadas.</span><span class="sxs-lookup"><span data-stu-id="248b2-265">In this case, the caller will hear no message or greeting before the call is handled by one of the options you select.</span></span> <span data-ttu-id="248b2-266">Você também pode carregar um arquivo de áudio (em formatos .wav, .mp3 ou. wma) ou criar uma saudação personalizada usando conversão de texto em fala.</span><span class="sxs-lookup"><span data-stu-id="248b2-266">You can also upload an audio file (in .wav, mp3 or .wma formats), or create a custom greeting using Text-to-Speech.</span></span>

- <span data-ttu-id="248b2-267">**Sem saudação** Nenhuma saudação será reproduzida quando as pessoas ligarem para o número de telefone do atendedor automático.</span><span class="sxs-lookup"><span data-stu-id="248b2-267">**No greeting** No greeting will be played when people call in to the auto attendant phone number.</span></span>
- <span data-ttu-id="248b2-268">**Carregar um arquivo de áudio** Se você escolher esta, grave a saudação de Natal e, em seguida, carregue o arquivo de áudio (nos formatos. wav,. mp3 ou. WMA)</span><span class="sxs-lookup"><span data-stu-id="248b2-268">**Upload an audio file** If you choose this, record the holiday greeting and then upload your audio file (in a .wav, .mp3 or .wma format)</span></span>
- <span data-ttu-id="248b2-269">**Digite uma mensagem de saudação** Se você escolher essa opção, insira o texto que deseja que o sistema Leia (até 1000 caracteres).</span><span class="sxs-lookup"><span data-stu-id="248b2-269">**Type a greeting message** If you choose this option, enter the text you want the system to read (up to 1000 characters).</span></span> <span data-ttu-id="248b2-270">Por exemplo, você pode inserir "Feliz ano novo!</span><span class="sxs-lookup"><span data-stu-id="248b2-270">For example, you might enter "Happy New Year!</span></span> <span data-ttu-id="248b2-271">Nossos escritórios estão fechados no momento."</span><span class="sxs-lookup"><span data-stu-id="248b2-271">Our offices are currently closed."</span></span> <span data-ttu-id="248b2-272">na caixa **digite uma mensagem de saudação** .</span><span class="sxs-lookup"><span data-stu-id="248b2-272">in the **Type a greeting message** box.</span></span>

![Ícone do número 4, fazendo referência a um texto explicativo na captura de tela anterior](media/sfbcallout4.png)

<span data-ttu-id="248b2-274">**Ação** Você pode selecionar o que acontece com as chamadas que chegam durante este feriado.</span><span class="sxs-lookup"><span data-stu-id="248b2-274">**Actions** You can select what happens to the calls that arrive during this holiday.</span></span> <span data-ttu-id="248b2-275">Você pode escolher entre as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="248b2-275">You can chose from the following options:</span></span>

- <span data-ttu-id="248b2-276">**Desconectar** A pessoa será desconectada após ouvir a saudação de feriado.</span><span class="sxs-lookup"><span data-stu-id="248b2-276">**Disconnect** The person calling in will be disconnected after hearing the holiday greeting.</span></span>
- <span data-ttu-id="248b2-277">**Redirecionar chamada** Isso pode ser usado para enviar a chamada automaticamente para:</span><span class="sxs-lookup"><span data-stu-id="248b2-277">**Redirect call** This can be used to automatically send the call to:</span></span>
  - <span data-ttu-id="248b2-278">Uma **Pessoa da sua empresa** com uma licença de **Sistema de Telefonia** habilitada para Enterprise Voice ou com Planos de Chamadas do Office 365 atribuídos.</span><span class="sxs-lookup"><span data-stu-id="248b2-278">A **Person in your company** with a **Phone System** license that is enabled for Enterprise Voice or assigned Calling Plans in Office 365.</span></span> <span data-ttu-id="248b2-279">Você pode configurá-lo para que o chamador possa ser enviado para a caixa postal.</span><span class="sxs-lookup"><span data-stu-id="248b2-279">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="248b2-280">Para fazer isso, selecione **pessoa em sua empresa**e defina esta pessoa para que as chamadas sejam encaminhadas diretamente para o correio de voz.</span><span class="sxs-lookup"><span data-stu-id="248b2-280">To do this, select **Person in your company**, and set this person to have their calls forwarded directly to voicemail.</span></span>

    > [!Note]
    > <span data-ttu-id="248b2-281">A **Pessoa da sua empresa** pode ser um usuário Online ou um usuário hospedado no local usando o Skype for Business Server 2015 ou o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="248b2-281">**Person in your company** can be an Online user or a user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013.</span></span>

   - <span data-ttu-id="248b2-282">**Aplicativo de voz** Selecione o nome de uma conta de recurso associada a uma fila de chamadas ou atendedor automático que já foi criado.</span><span class="sxs-lookup"><span data-stu-id="248b2-282">**Voice application** Select the name of a resource account associated to either a call queue or auto attendant that has already been created.</span></span>

    > [!Note]
    > <span data-ttu-id="248b2-283">Por padrão, todas as chamadas recebidas durante um período de feriado desconectam a pessoa após a saudação (se houver uma), portanto, você deve especificar um redirecionamento caso outro comportamento seja desejado.</span><span class="sxs-lookup"><span data-stu-id="248b2-283">By default, all calls arriving during a holiday period are set to disconnect after the greeting (if any), so you must specify a redirect if a different behavior is desired.</span></span>

<a name="dialscope"></a>
#### <a name="select-dial-scope-page"></a><span data-ttu-id="248b2-284">Página Selecionar escopo de discagem</span><span class="sxs-lookup"><span data-stu-id="248b2-284">Select dial scope page</span></span>

<span data-ttu-id="248b2-285">Nesta página, você pode configurar quais usuários em sua organização serão listados em seu diretório e disponíveis para discar por nome quando uma pessoa ligar para a sua organização.</span><span class="sxs-lookup"><span data-stu-id="248b2-285">On this page, you can set up which users in your organization will be listed in your directory and available for Dial by Name when a person that calls in to your organization.</span></span>

![Captura de tela mostrando a página de escopo de discagem](media/1bcb185c-00db-43a7-b5c4-9b021c0627f7.png)

* * *

<span data-ttu-id="248b2-287">![Ícone do número 1, fazendo referência a um texto explicativo na](media/sfbcallout1.png) captura de tela anterior usando a opção **incluir** , você tem duas opções:</span><span class="sxs-lookup"><span data-stu-id="248b2-287">![Icon of the number 1, referencing a callout in the previous screenshot](media/sfbcallout1.png) Using the **Include** option, you have two options:</span></span>

- <span data-ttu-id="248b2-288">**Todos os usuários online** O uso dessa opção permite que todas as pessoas da organização sejam incluídas na pesquisa do diretório.</span><span class="sxs-lookup"><span data-stu-id="248b2-288">**All Online users** Using this option allows all of the people in your organization to be included in directory search.</span></span> <span data-ttu-id="248b2-289">Todos os usuários online com uma licença do **sistema telefônico** , bem como os usuários hospedados no local usando o Skype for Business Server ou o Lync Server 2013 com planos de chamada no Office 365, serão listados.</span><span class="sxs-lookup"><span data-stu-id="248b2-289">All Online users with a **Phone System** license, as well as users hosted on-premises using Skype for Business Server or Lync Server 2013 who have Calling Plans in Office 365, will be listed.</span></span>
- <span data-ttu-id="248b2-290">**Grupo de usuários personalizado** Se você usar essa opção, poderá pesquisar um grupo, uma lista de distribuição ou um grupo de segurança do Office 365 que tenha sido criado em sua organização e as pessoas adicionadas a este grupo do Office 365, lista de distribuição ou grupo de segurança que sejam **usuários online com um Licença do sistema de telefone** ou hospedada no local usando o Skype for Business server 2015 ou o Lync server 2013.</span><span class="sxs-lookup"><span data-stu-id="248b2-290">**Custom user group** If you use this option, you can search for an Office 365 Group, distribution list, or security group that has been created in your organization, and the people added to this Office 365 Group, distribution list, or security group who are either **Online users with a Phone System license** or hosted on-premises using Skype for Business Server 2015 or Lync Server 2013.</span></span> <span data-ttu-id="248b2-291">Você pode adicionar vários grupos do Office 365, listas de distribuição e grupos de segurança.</span><span class="sxs-lookup"><span data-stu-id="248b2-291">You can add multiple Office 365 Groups, distribution lists, and security groups.</span></span>

* * *

![Ícone do número 2, fazendo referência a um texto explicativo na captura de tela anterior](media/sfbcallout2.png)

<span data-ttu-id="248b2-293">Usando a opção **excluir** , você tem duas opções:</span><span class="sxs-lookup"><span data-stu-id="248b2-293">Using the **Exclude** option, you have two options:</span></span>

- <span data-ttu-id="248b2-294">**Nenhuma** O uso desta opção indicará que nenhum usuário online será excluído da pesquisa de diretório.</span><span class="sxs-lookup"><span data-stu-id="248b2-294">**None** Using this option will indicate that no Online users will be excluded from directory search.</span></span>
- <span data-ttu-id="248b2-295">**Grupo de usuários personalizado** Se você usar essa opção, poderá pesquisar um grupo, uma lista de distribuição ou um grupo de segurança do Office 365 que tenha sido criado em sua organização, e todas as pessoas adicionadas a este grupo do Office 365, lista de distribuição ou grupos de segurança serão excluídas da pesquisa de diretório.</span><span class="sxs-lookup"><span data-stu-id="248b2-295">**Custom user group** If you use this option, you can search for an Office 365 Group, distribution list, or security group that has been created in your organization, and all people added to this Office 365 Group, distribution list, or security groups will be excluded from directory search.</span></span> <span data-ttu-id="248b2-296">Você pode adicionar vários grupos do Office 365, listas de distribuição e grupos de segurança.</span><span class="sxs-lookup"><span data-stu-id="248b2-296">You can add multiple Office 365 Groups, distribution lists, and security groups.</span></span>

> [!NOTE]
> <span data-ttu-id="248b2-297">Pode levar até 36 horas para que um novo usuário tenha o nome listado no diretório quando alguém usa discar por nome com reconhecimento de fala.</span><span class="sxs-lookup"><span data-stu-id="248b2-297">It might take up to 36 hours for a new user to have their name listed in the directory when someone uses Dial by Name with speech recognition.</span></span>

<span data-ttu-id="248b2-298">Depois de inserir todos os campos obrigatórios e configurar os menus e as opções de manipulação de chamadas, clique em **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="248b2-298">After you enter all the required fields and set up call handling menus and options, click **Submit**.</span></span>

## <a name="editing-and-testing-auto-attendants"></a><span data-ttu-id="248b2-299">Editando e testando atendedores automáticos</span><span class="sxs-lookup"><span data-stu-id="248b2-299">Editing and testing auto attendants</span></span>

<span data-ttu-id="248b2-300">Depois de ter salvo o atendedor automático, ele será listado na página **Atendedores automáticos**.</span><span class="sxs-lookup"><span data-stu-id="248b2-300">After you have saved your auto attendant, it will be listed on the **Auto attendants** page.</span></span> <span data-ttu-id="248b2-301">Isso permitirá que você veja rapidamente algumas das opções que você configurou, incluindo o nome, o número de telefone, o idioma e o status.</span><span class="sxs-lookup"><span data-stu-id="248b2-301">This will allow you to quickly see some of the options that you have set up, including the name, phone number, language, and status.</span></span>

<span data-ttu-id="248b2-302">Se você quiser fazer alterações em um atendedor automático, selecione o atendedor automático e, no painel Ação, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="248b2-302">If you want to make changes to an auto attendant, select the auto attendant, and then in the Action pane click **Edit**.</span></span>

<span data-ttu-id="248b2-303">Você também pode fazer uma chamada de teste rapidamente para o atendedor automático usando o botão **testar** no painel ação.</span><span class="sxs-lookup"><span data-stu-id="248b2-303">You can also quickly place a test call to your auto attendant by using the **Test** button in the Action pane.</span></span>

## <a name="auto-attendant-cmdlets"></a><span data-ttu-id="248b2-304">Cmdlets de atendedores automáticos</span><span class="sxs-lookup"><span data-stu-id="248b2-304">Auto attendant cmdlets</span></span>

<span data-ttu-id="248b2-305">Você também pode usar o Windows PowerShell para criar e configurar atendedores automáticos.</span><span class="sxs-lookup"><span data-stu-id="248b2-305">You can also use Windows PowerShell to create and set up auto attendants.</span></span> <span data-ttu-id="248b2-306">Estes são os cmdlets necessários para gerenciar um atendedor automático:</span><span class="sxs-lookup"><span data-stu-id="248b2-306">Here are the cmdlets that you need to manage an auto attendant:</span></span>

- [<span data-ttu-id="248b2-307">New-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="248b2-307">New-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant?view=skype-ps)  
- [<span data-ttu-id="248b2-308">Set-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="248b2-308">Set-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csautoattendant?view=skype-ps)
- [<span data-ttu-id="248b2-309">Get-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="248b2-309">Get-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant?view=skype-ps)
- [<span data-ttu-id="248b2-310">Get-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="248b2-310">Get-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csautoattendantholidays?view=skype-ps)
- [<span data-ttu-id="248b2-311">Remove-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="248b2-311">Remove-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csautoattendant?view=skype-ps)
- [<span data-ttu-id="248b2-312">New-CsAutoAttendantMenu</span><span class="sxs-lookup"><span data-stu-id="248b2-312">New-CsAutoAttendantMenu</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendantmenu?view=skype-ps)
- [<span data-ttu-id="248b2-313">New-CsOnlineAudioFile</span><span class="sxs-lookup"><span data-stu-id="248b2-313">New-CsOnlineAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineAudioFile?view=skype-ps)
- [<span data-ttu-id="248b2-314">New-CsAutoAttendantCallFlow</span><span class="sxs-lookup"><span data-stu-id="248b2-314">New-CsAutoAttendantCallFlow</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallFlow?view=skype-ps)
- [<span data-ttu-id="248b2-315">Export-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="248b2-315">Export-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/export-csorganizationalautoattendantholidays?view=skype-ps)
- [<span data-ttu-id="248b2-316">New-CsOnlineTimeRange</span><span class="sxs-lookup"><span data-stu-id="248b2-316">New-CsOnlineTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinetimerange?view=skype-ps)
- [<span data-ttu-id="248b2-317">New-CsOnlineDateTimeRange</span><span class="sxs-lookup"><span data-stu-id="248b2-317">New-CsOnlineDateTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinedatetimerange?view=skype-ps)
- [<span data-ttu-id="248b2-318">New-CsOnlineSchedule</span><span class="sxs-lookup"><span data-stu-id="248b2-318">New-CsOnlineSchedule</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsOnlineSchedule?view=skype-ps)
- [<span data-ttu-id="248b2-319">Get-CsAutoAttendantSupportedTimeZone</span><span class="sxs-lookup"><span data-stu-id="248b2-319">Get-CsAutoAttendantSupportedTimeZone</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone?view=skype-ps)
- [<span data-ttu-id="248b2-320">New-CsAutoAttendantCallHandlingAssociation</span><span class="sxs-lookup"><span data-stu-id="248b2-320">New-CsAutoAttendantCallHandlingAssociation</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation?view=skype-ps)
- [<span data-ttu-id="248b2-321">Get-CsAutoAttendantSupportedLanguage</span><span class="sxs-lookup"><span data-stu-id="248b2-321">Get-CsAutoAttendantSupportedLanguage</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage?view=skype-ps)
- [<span data-ttu-id="248b2-322">Import-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="248b2-322">Import-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csautoattendantholidays?view=skype-ps)
- [<span data-ttu-id="248b2-323">New-CsAutoAttendantCallableEntity</span><span class="sxs-lookup"><span data-stu-id="248b2-323">New-CsAutoAttendantCallableEntity</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallableEntity?view=skype-ps)

### <a name="more-about-windows-powershell"></a><span data-ttu-id="248b2-324">Mais sobre o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="248b2-324">More about Windows PowerShell</span></span>

- <span data-ttu-id="248b2-325">O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer.</span><span class="sxs-lookup"><span data-stu-id="248b2-325">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="248b2-326">Com o Windows PowerShell, você pode gerenciar o Office 365 e o Microsoft Teams usando um único ponto de administração que pode simplificar seu trabalho diário, quando você tem várias tarefas para fazer.</span><span class="sxs-lookup"><span data-stu-id="248b2-326">With Windows PowerShell, you can manage Office 365 and Microsoft Teams using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="248b2-327">Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="248b2-327">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="248b2-328">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="248b2-328">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [<span data-ttu-id="248b2-329">Por que você precisa usar o PowerShell do Office 365</span><span class="sxs-lookup"><span data-stu-id="248b2-329">Why you need to use Office 365 PowerShell</span></span>](https://docs.microsoft.com/en-us/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- <span data-ttu-id="248b2-330">O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade apenas usando o centro de administração do Microsoft 365, como quando você está usando alterações de configuração para muitos usuários de uma só vez.</span><span class="sxs-lookup"><span data-stu-id="248b2-330">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="248b2-331">Saiba mais sobre essas vantagens nos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="248b2-331">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="248b2-332">Gerenciar o Office 365 com o Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="248b2-332">Manage Office 365 with Office 365 PowerShell</span></span>](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [<span data-ttu-id="248b2-333">Usar o Windows PowerShell para gerenciar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="248b2-333">Using Windows PowerShell to manage Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a><span data-ttu-id="248b2-334">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="248b2-334">Related topics</span></span>

[<span data-ttu-id="248b2-335">Veja aqui o que você obtém com o Sistema de Telefonia no Office 365</span><span class="sxs-lookup"><span data-stu-id="248b2-335">Here's what you get with Phone System in Office 365</span></span>](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[<span data-ttu-id="248b2-336">Obter números de telefone de serviço</span><span class="sxs-lookup"><span data-stu-id="248b2-336">Getting service phone numbers</span></span>](/microsoftteams/getting-service-phone-numbers)

[<span data-ttu-id="248b2-337">Disponibilidade de audioconferência e planos de chamadas por país e região</span><span class="sxs-lookup"><span data-stu-id="248b2-337">Country and region availability for Audio Conferencing and Calling Plans</span></span>](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

[<span data-ttu-id="248b2-338">New-CsOrganizationalAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="248b2-338">New-CsOrganizationalAutoAttendant</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/new-csorganizationalautoattendant?view=skype-ps)  

[<span data-ttu-id="248b2-339">Quais são os atendedores automáticos do Cloud?</span><span class="sxs-lookup"><span data-stu-id="248b2-339">What are Cloud auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)

[<span data-ttu-id="248b2-340">Exemplo de pequenas empresas - Configurar um atendedor automático</span><span class="sxs-lookup"><span data-stu-id="248b2-340">Small business example - Set up an auto attendant</span></span>](/microsoftteams/tutorial-org-aa)  
