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
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Saiba como configurar e testar os atendedores automáticos de nuvem para eficiente tratamento de chamadas para sua organização.
ms.openlocfilehash: e98233bd610cd83afdbc727a5edeba77951d1989
ms.sourcegitcommit: ca7a22da082ac5336f31ffd76f3d4aef6c76285b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/10/2019
ms.locfileid: "33868812"
---
# <a name="set-up-a-cloud-auto-attendant"></a><span data-ttu-id="93419-103">Configurar um atendedor automático do Cloud</span><span class="sxs-lookup"><span data-stu-id="93419-103">Set up a Cloud auto attendant</span></span>

<span data-ttu-id="93419-104">Atendedores automáticos permitem que as pessoas que ligam para sua organização e navegue para conectá-los ao departamento direita, chame a fila, pessoa ou o operador de um sistema de menus.</span><span class="sxs-lookup"><span data-stu-id="93419-104">Auto attendants let people that call in to your organization and navigate a menu system to get them to the right department, call queue, person, or the operator.</span></span> <span data-ttu-id="93419-105">Você pode criar um atendedor automático para sua organização usando o Centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="93419-105">You can create an auto attendant for your organization by using the Microsoft Teams admin center.</span></span> <span data-ttu-id="93419-106">Para criar um novo atendedor automático, vá para **voz** no painel de navegação esquerdo e selecione **atendedores automáticos** > **Adicionar novo**.</span><span class="sxs-lookup"><span data-stu-id="93419-106">To create a new auto attendant, go to **Voice** in the left navigation, and then select **Auto attendants** > **Add new**.</span></span>

<span data-ttu-id="93419-107">Se você deseja saber mais sobre os atendedores automáticos, consulte [Cite atendedores automáticos de nuvem?](/microsoftteams/what-are-phone-system-auto-attendants)</span><span class="sxs-lookup"><span data-stu-id="93419-107">If you want to learn more about auto attendants, see [What are Cloud auto attendants?](/microsoftteams/what-are-phone-system-auto-attendants)</span></span>

> [!NOTE]
> <span data-ttu-id="93419-108">Este artigo se aplica ao Microsoft Teams e Skype para Business Online.</span><span class="sxs-lookup"><span data-stu-id="93419-108">This article applies to both Microsoft Teams and Skype for Business Online.</span></span>



## <a name="step-1---get-started"></a><span data-ttu-id="93419-109">Etapa 1 - Introdução</span><span class="sxs-lookup"><span data-stu-id="93419-109">Step 1 - Get started</span></span>

- <span data-ttu-id="93419-110">Um atendedor automático é necessário ter uma conta de recurso associado.</span><span class="sxs-lookup"><span data-stu-id="93419-110">An auto attendant is required to have an associated resource account.</span></span> <span data-ttu-id="93419-111">Consulte [Gerenciar contas de recursos em equipes](manage-resource-accounts.md) para obter detalhes sobre as contas de recursos.</span><span class="sxs-lookup"><span data-stu-id="93419-111">See [Manage resource accounts in Teams](manage-resource-accounts.md) for details on resource accounts.</span></span>
- <span data-ttu-id="93419-112">Se você planeja atribua um número de roteamento direto, você precisará adquirir e atribuir as seguintes licenças às suas contas de recurso \(Office 365 Enterprise E1, E3 ou E5, com o complemento de sistema telefônico\).</span><span class="sxs-lookup"><span data-stu-id="93419-112">If you plan to assign a Direct Routing number, you need to acquire and assign the following licenses to your resource accounts \(Office 365 Enterprise E1, E3 or E5, with the Phone System add-on\).</span></span>
- <span data-ttu-id="93419-113">Se você estiver atribuindo um número de serviço da Microsoft em vez disso, você precisará adquirir e atribuir as seguintes licenças à sua conta do recurso \(Office 365 Enterprise E1, E3 ou E5, com o complemento de sistema telefônico e um plano de chamar\).</span><span class="sxs-lookup"><span data-stu-id="93419-113">If you are assigning a Microsoft service number instead, you need to acquire and assign the following licenses to your resource account \(Office 365 Enterprise E1, E3 or E5, with the Phone System add-on and a Calling Plan\).</span></span>

> [!NOTE] 
> <span data-ttu-id="93419-114">Microsoft está trabalhando em um modelo de licenciamento apropriado para aplicativos como atendedores automáticos de nuvem e filas de chamada, para agora você precisa usar o modelo de licenciamento por usuário.</span><span class="sxs-lookup"><span data-stu-id="93419-114">Microsoft is working on an appropriate licensing model for applications such as Cloud auto attendants and call queues, for now you need to use the user-licensing model.</span></span>

> [!CAUTION]
> <span data-ttu-id="93419-115">Para obter e usar números de telefone gratuitos, você precisa configurar Créditos de Comunicação.</span><span class="sxs-lookup"><span data-stu-id="93419-115">To get and use toll-free phone numbers, you need to set up Communications Credits.</span></span> <span data-ttu-id="93419-116">Para fazer isso, consulte [O que são Créditos de Comunicação?](what-are-communications-credits.md) e [Configurar Créditos de Comunicação para a sua organização](set-up-communications-credits-for-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="93419-116">To do this see [What are Communications Credits?](what-are-communications-credits.md) and [Set up Communications Credits for your organization](set-up-communications-credits-for-your-organization.md).</span></span>

> [!TIP]
> <span data-ttu-id="93419-117">Para redirecionar chamadas para um operador ou uma opção de menu que é um usuário Online com uma licença de **Sistema telefônico** , você precisará habilitá-los para o Enterprise Voice ou atribuir chamar planos no Office 365 para acessá-los.</span><span class="sxs-lookup"><span data-stu-id="93419-117">To redirect calls to an operator or a menu option that is an Online user with a **Phone System** license, you will need to enable them for Enterprise Voice or assign Calling Plans in Office 365 to them.</span></span> <span data-ttu-id="93419-118">Consulte [Atribuir Skype para licenças de negócios](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) ou [equipes da Microsoft atribuir licenças](assign-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="93419-118">See [Assign Skype for Business licenses](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) or [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="93419-119">Você também pode usar o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="93419-119">You can also use Windows PowerShell.</span></span> <span data-ttu-id="93419-120">Por exemplo, execute:`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="93419-120">For example, run: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

## <a name="step-2---create-a-new-auto-attendant"></a><span data-ttu-id="93419-121">Etapa 2 - Criar um novo atendedor automático</span><span class="sxs-lookup"><span data-stu-id="93419-121">Step 2 - Create a new auto attendant</span></span>

> [!IMPORTANT]
> <span data-ttu-id="93419-122">Cada atendedor automático é necessário ter uma [conta do recurso](manage-resource-accounts.md)de associada.</span><span class="sxs-lookup"><span data-stu-id="93419-122">Every auto attendant is required to have an associated [resource account](manage-resource-accounts.md).</span></span> <span data-ttu-id="93419-123">Você deve criar a conta do recurso primeiro, depois você pode associá-lo para o atendedor automático.</span><span class="sxs-lookup"><span data-stu-id="93419-123">You must create the resource account first, then you can associate it to the auto attendant.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="93419-124">Usando o Centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="93419-124">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="93419-125">No **Centro de administração de equipes da Microsoft**, clique em **voz** > **atendedores automáticos**, clique em **+ novo**:</span><span class="sxs-lookup"><span data-stu-id="93419-125">In the **Microsoft Teams admin center**, click   **Voice** > **Auto attendants**, then click **+ New**:</span></span>

#### <a name="general-info-page"></a><span data-ttu-id="93419-126">Página de informações gerais</span><span class="sxs-lookup"><span data-stu-id="93419-126">General info page</span></span>

![New auto attendant page 1.](media/edacec94-9384-4a87-be0a-5c49a151287e.png)

* * *

![Número 1](media/sfbcallout1.png)

<span data-ttu-id="93419-129">**Nome** Insira um nome de exibição descritivo para o atendedor automático.</span><span class="sxs-lookup"><span data-stu-id="93419-129">**Name** Enter a descriptive display name for your auto attendant.</span></span> <span data-ttu-id="93419-130">O nome é obrigatório e pode conter até 64 caracteres, incluindo espaços.</span><span class="sxs-lookup"><span data-stu-id="93419-130">The name is required and can contain up to 64 characters, including spaces.</span></span> <span data-ttu-id="93419-131">Ele será listado na coluna **Nome** da guia **Atendedores automáticos**.</span><span class="sxs-lookup"><span data-stu-id="93419-131">It will be listed in the **Name** column on the **Auto attendants** tab.</span></span>

* * *

![Número 2](media/sfbcallout2.png)

<span data-ttu-id="93419-133">**Conta do recurso** Clique nesse botão para selecionar uma ou mais contas de recurso para se conectar ao seu novo atendedor automático.</span><span class="sxs-lookup"><span data-stu-id="93419-133">**Resource account** Click this button to select one or more resource accounts to connect to your new auto attendant.</span></span> <span data-ttu-id="93419-134">Todos os atendedores automáticos de são necessários para ter uma conta de recurso associado.</span><span class="sxs-lookup"><span data-stu-id="93419-134">All auto attendants are required to have an associated resource account.</span></span> <span data-ttu-id="93419-135">Uma conta de recurso pode ter um número de telefone associado à conta, mas talvez não.</span><span class="sxs-lookup"><span data-stu-id="93419-135">A resource account can have a phone number associated to the account, but it might not.</span></span> <span data-ttu-id="93419-136">Um atendedor automático de nível superior geralmente têm uma conta de recurso com um número de telefone atribuído, mas AutoAttendant aninhados (usado como um menu de nível 2 que o atendedor automático de nível da primeiro conecta-se à) pode não ter um número de telefone atribuído a sua conta do recurso.</span><span class="sxs-lookup"><span data-stu-id="93419-136">A top-level auto attendant usually have a resource account with an assigned phone number, but nested auto attendant (used as a level 2 menu that the first level auto attendant connects to) might not have a phone number assigned to its resource account.</span></span>

* * *

![Número 3](media/sfbcallout3.png)

<span data-ttu-id="93419-p108">**Fuso horário** Você deve definir o fuso horário para o atendedor automático, mas ele não precisa corresponder ao fuso horário do endereço principal de sua organização. Cada atendedor automático pode ter um fuso horário diferente e os horários comerciais definidos para o atendedor automático serão definidos com base no fuso horário que você selecionar aqui.</span><span class="sxs-lookup"><span data-stu-id="93419-p108">**Time zone** You must set the time zone for your auto attendant, but it doesn't need to correspond to the time zone of the main address listed for your organization. Each auto attendant can have a different time zone, and the business hours set for the auto attendant will be set based on the time zone that you select here.</span></span>

* * *

![Número 4](media/sfbcallout4.png)

<span data-ttu-id="93419-141">**Idioma** Selecione o idioma que você deseja usar para o atendedor automático entre os idiomas disponíveis listados.</span><span class="sxs-lookup"><span data-stu-id="93419-141">**Language** Select the language that you want to use for your auto attendant from any of the available languages listed.</span></span> <span data-ttu-id="93419-142">O idioma que você definir aqui é o idioma que o atendedor automático usará para interagir com pessoas que ligam para este atendedor automático e todo os sistema os avisos serão reproduzidos neste idioma.</span><span class="sxs-lookup"><span data-stu-id="93419-142">The language you set here is the language that the auto attendant will use to interact with people that call in to this auto attendant, and all the system prompts will be played in this language.</span></span>

* * *

![Número 5](media/sfbcallout5.png)

<span data-ttu-id="93419-144">**Operador** Isso é opcional e não precisa ser definido para o atendedor automático.</span><span class="sxs-lookup"><span data-stu-id="93419-144">**Operator** This is optional and doesn't need to be set for the auto attendant.</span></span> <span data-ttu-id="93419-145">No entanto, você pode definir a opção de **operador** para pessoas que ligam para ser capaz de quebrar sem os menus para falar com uma pessoa para ajudá-los.</span><span class="sxs-lookup"><span data-stu-id="93419-145">However, you can set the **Operator** option for people that call in to be able to break out of the menus to speak to a person to help them.</span></span>

<span data-ttu-id="93419-146">A tecla 0 é atribuída automaticamente ao Operador.</span><span class="sxs-lookup"><span data-stu-id="93419-146">The key 0 is automatically assigned to Operator.</span></span>

<span data-ttu-id="93419-147">Se você configurar isso, você também precisará informar as pessoas a quem chamar que isso é uma opção disponível em **Opções de menu de edição** , na página de **tratamento de chamada do horário comercial** .</span><span class="sxs-lookup"><span data-stu-id="93419-147">If you set this up, you will also need to tell people who call in that this is an available option in the **Edit menu options** on the **Business hours call handling** page.</span></span> <span data-ttu-id="93419-148">Se você definir um operador na sua atendedor automático, você precisará inserir o texto de aviso correspondente na caixa **os chamadores ouvirão** ou alterar seu arquivo de áudio para incluir essa opção.</span><span class="sxs-lookup"><span data-stu-id="93419-148">If you set an operator on your auto attendant, you will need to enter the corresponding prompt text in the **Callers will hear** box or change your audio file to include this option.</span></span> <span data-ttu-id="93419-149">Por exemplo, "Para falar com o operador, pressione 0".</span><span class="sxs-lookup"><span data-stu-id="93419-149">For example, "For the Operator, press zero."</span></span>

<span data-ttu-id="93419-150">Você pode definir um dos seguintes como Operador:</span><span class="sxs-lookup"><span data-stu-id="93419-150">You can set one of the following as Operator:</span></span>

- <span data-ttu-id="93419-151">**Pessoa da sua empresa** com uma licença de **Sistema de Telefonia** habilitada para Enterprise Voice ou com Planos de Chamadas do Office 365 atribuídos.</span><span class="sxs-lookup"><span data-stu-id="93419-151">**Person in your company** with a **Phone System** license that is enabled for Enterprise Voice or assigned Calling Plans in Office 365.</span></span>

     > [!Note]
     > <span data-ttu-id="93419-152">A **Pessoa da sua empresa** pode ser um usuário Online ou um usuário hospedado no local usando o Skype for Business Server 2015 ou o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="93419-152">**Person in your company** can be an Online user or a user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013.</span></span>

- <span data-ttu-id="93419-153">Uma **fila de chamadas** que você definiu.</span><span class="sxs-lookup"><span data-stu-id="93419-153">A **call queue** that you have set up.</span></span>
- <span data-ttu-id="93419-154">Você pode configurá-lo para que a pessoa que liga seja enviada para a caixa postal.</span><span class="sxs-lookup"><span data-stu-id="93419-154">You can set it up so the person calling will be sent to voicemail.</span></span> <span data-ttu-id="93419-155">Para fazer isso, selecione **a pessoa da sua empresa** e defina as chamadas sejam encaminhadas diretamente para a caixa postal dessa pessoa.</span><span class="sxs-lookup"><span data-stu-id="93419-155">To do this, select **Person in your company** and set this person's calls to be forwarded directly to voicemail.</span></span>

* * *

![Número 6](media/sfbcallout6.png)

<span data-ttu-id="93419-157">**Habilitar entradas de voz** Reconhecimento de fala está disponível se esta opção está selecionada.</span><span class="sxs-lookup"><span data-stu-id="93419-157">**Enable voice inputs** Speech recognition is available if this option is selected.</span></span> <span data-ttu-id="93419-158">Pessoas que chamam no podem usar a entrada de voz no [idioma definido](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="93419-158">People that call in can use voice input in the  [language you set](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span></span> <span data-ttu-id="93419-159">Você pode desativar o reconhecimento de fala, definindo-la como desativado, se você quiser apenas permitir que as pessoas usam do teclado do telefone.</span><span class="sxs-lookup"><span data-stu-id="93419-159">You can disable speech recognition by setting it to off if you want to only let people use their phone keypad.</span></span>

* * *

<span data-ttu-id="93419-160">Quando você terminar com suas seleções, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="93419-160">When you are finished with your selections, click on **Next**.</span></span>

#### <a name="business-hours-page"></a><span data-ttu-id="93419-161">Página de horário comercial</span><span class="sxs-lookup"><span data-stu-id="93419-161">Business hours page</span></span>

<span data-ttu-id="93419-162">Por padrão, o horário comercial é definido para 9 am a 17: 00, de segunda à sexta-feira.</span><span class="sxs-lookup"><span data-stu-id="93419-162">By default, business hours are set to 9am to 5pm, Monday through Friday.</span></span>  <span data-ttu-id="93419-163">Todos os horários que não estão incluídos nos horários comerciais são considerados horários fora do expediente.</span><span class="sxs-lookup"><span data-stu-id="93419-163">All of the hours that aren't included in business hours are considered after business hours.</span></span> <span data-ttu-id="93419-164">Você pode clicar em **Selecione 24/7** para tornar todos os horários de expediente.</span><span class="sxs-lookup"><span data-stu-id="93419-164">You can click on **Select 24/7** to make all hours business hours.</span></span> <span data-ttu-id="93419-165">A menos que você selecione a opção **Select 24/7** , a página **depois de configurações de chamadas de horas** será usada para configurar a tratamento de chamadas para após o horário comercial para o atendedor automático.</span><span class="sxs-lookup"><span data-stu-id="93419-165">Unless you select the **Select 24/7** option, the **After hours call settings** page will be used to configure the call handling for after business hours for the auto attendant.</span></span>

![New auto attendant Hours of operation.](media/61769547-cdb4-45c0-af5a-3d6e0731fbc6.png)

* * *

![Número 1](media/sfbcallout1.png)

<span data-ttu-id="93419-168">Por padrão, o horário comercial é definido de segunda à sexta-feira, das 9:00 am - 5:00 pm.</span><span class="sxs-lookup"><span data-stu-id="93419-168">By default, business hours are set to Monday to Friday, 9:00 am-5:00 pm.</span></span> <span data-ttu-id="93419-169">Selecione opção **Limpar todas as horas** para desmarcar todas as horas horários da agenda.</span><span class="sxs-lookup"><span data-stu-id="93419-169">Select **Clear all hours** option to unselect all hours hours in the schedule.</span></span> <span data-ttu-id="93419-170">Quando você seleciona **Redefinir como padrão**, de segunda à sexta-feira, das 9:00 am - 5:00 pm será redefinido horário comercial.</span><span class="sxs-lookup"><span data-stu-id="93419-170">When you select **Reset to default**, business hours will be reset to Monday to Friday, 9:00 am-5:00 pm.</span></span>

* * *

![Número 2](media/sfbcallout2.png)

<span data-ttu-id="93419-172">Para alterar os horários comerciais, destaque os horários comerciais que deseja definir usando o calendário.</span><span class="sxs-lookup"><span data-stu-id="93419-172">To change business hours, highlight the business hours you want to set using the calendar.</span></span> <span data-ttu-id="93419-173">O calendário permite que você selecione horários comerciais em intervalos de 30 minutos, e o horário comercial que você selecionar aqui será definido com base no fuso horário que você definiu na página **Geral info** .</span><span class="sxs-lookup"><span data-stu-id="93419-173">The calendar allows you to select business hours in 30-minute intervals, and the business hours you select here will be set based on the time zone that you set on the **General info** page.</span></span> <span data-ttu-id="93419-174">Para configurar um intervalo (horário de almoço, por exemplo), desmarque ou arraste para desmarcar o horário no calendário.</span><span class="sxs-lookup"><span data-stu-id="93419-174">To set up a break (a lunch break, for example), deselect or drag to deselect the time on the calendar.</span></span> <span data-ttu-id="93419-175">Você pode definir várias quebras em horário comercial.</span><span class="sxs-lookup"><span data-stu-id="93419-175">You can set multiple breaks within business hours.</span></span>

* * *

<span data-ttu-id="93419-176">Quando você terminar com suas seleções, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="93419-176">When you are finished with your selections, click on **Next**.</span></span>

#### <a name="business-hours-call-settings"></a><span data-ttu-id="93419-177">Configurações de chamadas do horário comercial</span><span class="sxs-lookup"><span data-stu-id="93419-177">Business hours call settings</span></span>

> [!TIP]
> <span data-ttu-id="93419-178">Se você usar uma agenda de horário comercial personalizado, você também precisará configurar uma chamada de manusear para após o horário comercial usando a página **após o horário de tratamento de chamada** , que fornecerá a você as mesmas opções como **configurações de chamadas do horário comercial**.</span><span class="sxs-lookup"><span data-stu-id="93419-178">If you use a custom business hours schedule, you will also need to set up call handing for after business hours using the **After hours call handling** page, which will give you the same options as **Business hours call settings**.</span></span>

<span data-ttu-id="93419-179">Você pode configurar saudações e prompts menus que as pessoas que a chamada no número de telefone do atendedor automático da sua organização ouvirá durante o horário comercial.</span><span class="sxs-lookup"><span data-stu-id="93419-179">You can set up greetings, prompts, and menus that people who call in to your organization's auto attendant phone number will hear during the business hours.</span></span>

<span data-ttu-id="93419-180">![Tratamento de chamada do horário comercial. ](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)
 ![Horário comercial continuado de tratamento de chamada.](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8b.png)</span><span class="sxs-lookup"><span data-stu-id="93419-180">![Business hours call handling.](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)
![Business hours call handling continued.](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8b.png)</span></span>

* * *

![Número 1](media/sfbcallout1.png)

<span data-ttu-id="93419-182">**Saudação** Uma saudação para horário comercial é opcional e pode ser definida como **Nenhuma saudação**.</span><span class="sxs-lookup"><span data-stu-id="93419-182">**Greeting** A business hours greeting is optional and can be set to **No greeting**.</span></span> <span data-ttu-id="93419-183">Nesse caso, o chamador não será ouvida nenhuma mensagem ou saudação antes que a chamada é atendida por uma das ações que você selecionar.</span><span class="sxs-lookup"><span data-stu-id="93419-183">In this case, the caller will hear no message or greeting before the call is handled by one of the actions you select.</span></span> <span data-ttu-id="93419-184">Você também pode carregar um arquivo de áudio (em formatos .wav, .mp3 ou. wma) ou criar uma saudação personalizada usando conversão de texto em fala.</span><span class="sxs-lookup"><span data-stu-id="93419-184">You can also upload an audio file (in .wav, mp3 or .wma formats), or create a custom greeting using Text-to-Speech.</span></span>

- <span data-ttu-id="93419-185">**Nenhum saudação** Nenhum saudação será reproduzida quando as pessoas ligam para o número de telefone do atendedor automático.</span><span class="sxs-lookup"><span data-stu-id="93419-185">**No greeting** No greeting will be played when people call in to the auto attendant phone number.</span></span>
- <span data-ttu-id="93419-186">**Carregar um arquivo de áudio** Se você escolher essa opção, gravar a saudação e, em seguida, carregue o seu arquivo de áudio (em um formato. wav,. mp3 ou. wma).</span><span class="sxs-lookup"><span data-stu-id="93419-186">**Upload an audio file** If you choose this, record the greeting and then upload your audio file (in a .wav, .mp3 or .wma format).</span></span>
- <span data-ttu-id="93419-187">**Digite uma mensagem de saudação** Se você escolher essa opção, insira o texto que você deseja que o sistema para ler (até 1000 caracteres).</span><span class="sxs-lookup"><span data-stu-id="93419-187">**Type a greeting message** If you choose this option, enter the text you want the system to read (up to 1000 characters).</span></span> <span data-ttu-id="93419-188">Por exemplo, você pode inserir "Bem-vindo à Contoso.</span><span class="sxs-lookup"><span data-stu-id="93419-188">For example, you might enter "Welcome to Contoso.</span></span> <span data-ttu-id="93419-189">A sua ligação é muito importante para nós."</span><span class="sxs-lookup"><span data-stu-id="93419-189">Your call is important to us."</span></span> <span data-ttu-id="93419-190">na caixa **Os chamadores ouvirão**.</span><span class="sxs-lookup"><span data-stu-id="93419-190">in the **Callers will hear** box.</span></span>

* * *

![Número 2](media/sfbcallout2.png)

<span data-ttu-id="93419-192">Você pode selecionar o que acontece às chamadas que chegam durante o horário comercial.</span><span class="sxs-lookup"><span data-stu-id="93419-192">You can select what happens to calls that arrive during business hours.</span></span> <span data-ttu-id="93419-193">É possível escolher entre as seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="93419-193">You can chose from the following actions:</span></span>

- <span data-ttu-id="93419-194">**Desconectar** Se você selecionar a ele, a pessoa chamando em será desconectada depois de ouvir uma saudação para horário comercial.</span><span class="sxs-lookup"><span data-stu-id="93419-194">**Disconnect** If you select it, the person calling in will be disconnected after hearing a business hours greeting.</span></span>
- <span data-ttu-id="93419-195">**Redirecionar chamada** Isso pode ser usado para enviar a chamada automaticamente para:</span><span class="sxs-lookup"><span data-stu-id="93419-195">**Redirect call** This can be used to automatically send the call to:</span></span>
  - <span data-ttu-id="93419-196">**Pessoa da empresa** com uma licença de **Sistema telefônico** que está habilitada para Enterprise Voice ou atribuída chamar planos no Office 365.</span><span class="sxs-lookup"><span data-stu-id="93419-196">**Person in company** with a **Phone System** license that is enabled for Enterprise Voice or assigned Calling Plans in Office 365.</span></span> <span data-ttu-id="93419-197">Você pode configurá-lo para que o chamador possa ser enviado para a caixa postal.</span><span class="sxs-lookup"><span data-stu-id="93419-197">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="93419-198">Para fazer isso, selecione **a pessoa da empresa** e defina essa pessoa para que suas chamadas encaminhadas diretamente para a caixa postal.</span><span class="sxs-lookup"><span data-stu-id="93419-198">To do this, select **Person in company** and set this person to have their calls forwarded directly to voicemail.</span></span>

    > [!Note]
    > <span data-ttu-id="93419-199">**Pessoa da empresa** pode ser um usuário Online ou um usuário hospedado no local usando Skype para Business Server 2015 ou o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="93419-199">**Person in company** can be an Online user or a user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013.</span></span>

   - <span data-ttu-id="93419-200">Outro **atendedor automático**</span><span class="sxs-lookup"><span data-stu-id="93419-200">Another **Auto attendant**</span></span>

   <span data-ttu-id="93419-201">Você pode usar um atendedor automático existente para criar um segundo nível das opções de menu que contém um submenu.</span><span class="sxs-lookup"><span data-stu-id="93419-201">You can use an existing auto attendant to create a second level of menu options containing a sub-menu.</span></span> <span data-ttu-id="93419-202">These are called nested auto attendants.</span><span class="sxs-lookup"><span data-stu-id="93419-202">These are called nested auto attendants.</span></span> <span data-ttu-id="93419-203">Para enviar a chamada para um atendedor automático aninhados, selecione a **pessoa na empresa** e atribuir uma conta de recurso, um que já tenha um atendedor automático associado ou um que você irá associar a um atendedor automático depois que terminar criando este atendedor automático.</span><span class="sxs-lookup"><span data-stu-id="93419-203">To send the call to a nested auto attendant, select **Person in company** and assign a resource account, either one that already has an associated auto attendant or one that you will associate to an auto attendant once you are done creating this auto attendant.</span></span>

- <span data-ttu-id="93419-204">**Opções de menu de reprodução** também pode ser usado para permitir que você defina um prompt a que ser reproduzido.</span><span class="sxs-lookup"><span data-stu-id="93419-204">**Play menu options** can also be used to let you set up a prompt you want played.</span></span>

* * *

![Número 3](media/sfbcallout3.png)

<span data-ttu-id="93419-206">**Prompt do menu** Para criar o prompt do menu principal, você pode usar a conversão de texto em fala ou carregar um arquivo de áudio (.wav, .mp3 ou .wma).</span><span class="sxs-lookup"><span data-stu-id="93419-206">**Menu prompt** To create main menu prompt, you can either use Text-to-Speech or upload an audio file (.wav, .mp3 or .wma).</span></span> <span data-ttu-id="93419-207">Você pode digitar o prompt na caixa **definir sua navegação de menu para os chamadores** ou registrar um arquivo de áudio e dizer, por exemplo: "para vendas, diga ou pressione ou dizer 1.</span><span class="sxs-lookup"><span data-stu-id="93419-207">You can type the prompt in the **Set your menu navigation for callers** box or record an audio file and say, for example: "For Sales, say or press or say 1.</span></span> <span data-ttu-id="93419-208">Para Serviços, pressione ou fale 2.</span><span class="sxs-lookup"><span data-stu-id="93419-208">For Services, press or say 2.</span></span> <span data-ttu-id="93419-209">Para Suporte ao Cliente, pressione ou fale 3.</span><span class="sxs-lookup"><span data-stu-id="93419-209">For Customer Support, press or say 3.</span></span> <span data-ttu-id="93419-210">Para falar com o operador, pressione ou fale 0.</span><span class="sxs-lookup"><span data-stu-id="93419-210">For the operator, press or say 0.</span></span> <span data-ttu-id="93419-211">Para ouvir este menu novamente, pressione a tecla de asterisco ou fale repetir".</span><span class="sxs-lookup"><span data-stu-id="93419-211">To hear this menu again, press the star key or say repeat."</span></span> <span data-ttu-id="93419-212">**Digite uma mensagem de saudação** Se você escolher essa opção, você deve inserir o texto que você deseja que o sistema para ler (até 1000 caracteres).</span><span class="sxs-lookup"><span data-stu-id="93419-212">**Type a greeting message** If you chose this, you should enter the text you want the system to read (up to 1000 characters).</span></span> <span data-ttu-id="93419-213">**Carregar um arquivo de áudio** Se você escolher isso, deverá gravar a saudação e depois carregar o arquivo de áudio (nos formatos .wav, .mp3 ou .wma).</span><span class="sxs-lookup"><span data-stu-id="93419-213">**Upload an audio file** If you chose this, you will need to record the greeting and then upload your audio file (in a .wav, mp3 or .wma format).</span></span>

* * *

![Número 4](media/sfbcallout4.png)

<span data-ttu-id="93419-215">**Configuração de opções de menu** Opções de menu usando botões de tecla no teclado podem ser adicionadas ou removidas.</span><span class="sxs-lookup"><span data-stu-id="93419-215">**Menu options setup** Menu options using key buttons on the keypad can be added or removed.</span></span> <span data-ttu-id="93419-216">Para adicionar uma opção de menu, pressione **+ atribuir uma tecla de discagem**.</span><span class="sxs-lookup"><span data-stu-id="93419-216">To add a menu option, press **+ Assign a dial key**.</span></span> <span data-ttu-id="93419-217">Uma linha correspondente das opções serão exibidos abaixo.</span><span class="sxs-lookup"><span data-stu-id="93419-217">A corresponding row of options will appear below.</span></span> <span data-ttu-id="93419-218">Para excluir uma opção de menu, clique no lado esquerdo da chave correspondente no controle do teclado e clique no ícone Excluir acima.</span><span class="sxs-lookup"><span data-stu-id="93419-218">To delete a menu option, simply click to the left of the corresponding key on the keypad control and click on the delete icon above.</span></span> <span data-ttu-id="93419-219">A linha de mapeamento de teclas será removida.</span><span class="sxs-lookup"><span data-stu-id="93419-219">The key mapping row will be removed.</span></span>

> [!TIP]
> <span data-ttu-id="93419-220">Você precisará atualizar o texto de prompts de menu ou gravar novamente o áudio separadamente ao adicionar a removendo opções porque ele não será feito automaticamente para o prompt do menu existente.</span><span class="sxs-lookup"><span data-stu-id="93419-220">You will have to update menu prompts text or re-record the audio separately when adding to removing options because it won't be automatically done for the existing menu prompt.</span></span>  
>
><span data-ttu-id="93419-221">Qualquer opção de menu pode ser adicionada e removida em qualquer ordem, e os mapeamentos de teclas não precisam ser contínuo.</span><span class="sxs-lookup"><span data-stu-id="93419-221">Any menu option can be added and removed in any order, and the key mappings don't have to be continuous.</span></span> <span data-ttu-id="93419-222">Por exemplo, é possível, para criar um menu com as teclas de 0, 1 e 3 mapeadas para opções, enquanto a tecla 2 não será usada.</span><span class="sxs-lookup"><span data-stu-id="93419-222">It is possible, for example, to create a menu with keys 0, 1, and 3 mapped to options, while the key 2 isn't used.</span></span>

> [!NOTE]
> <span data-ttu-id="93419-223">As chaves \* (repetir) e \# (novamente) são reservados pelo sistema e não pode ser reatribuído.</span><span class="sxs-lookup"><span data-stu-id="93419-223">The keys \* (Repeat) and \# (Back) are reserved by the system and can't be reassigned.</span></span> <span data-ttu-id="93419-224">Se o reconhecimento de fala estiver habilitado, pressionando \* corresponderá com "Repetir" e # corresponderá com os comandos de voz "Volta".</span><span class="sxs-lookup"><span data-stu-id="93419-224">If speech recognition is enabled, pressing \* will correspond with "Repeat" and # will correspond with the "Back" voice commands.</span></span>

<span data-ttu-id="93419-225">Para configurar suas opções de menu, depois de selecionar as teclas de discagem, você precisará:</span><span class="sxs-lookup"><span data-stu-id="93419-225">To set up your menu options, after you select the dial key(s), you will need to:</span></span>

- <span data-ttu-id="93419-226">Insira o **comando de voz** da opção.</span><span class="sxs-lookup"><span data-stu-id="93419-226">Enter the **Voice command**  of the option.</span></span> <span data-ttu-id="93419-227">Isso pode ter até 64 caracteres de comprimento e pode conter várias palavras como "E atendimento"ao cliente ou"operações pó."</span><span class="sxs-lookup"><span data-stu-id="93419-227">This can be up to 64 characters long, and can contain multiple words like "Customer Service" or "Operations and Grounds."</span></span> <span data-ttu-id="93419-228">Se o reconhecimento de fala está habilitado, o nome será reconhecido automaticamente e a pessoa chamando em poderão Pressione 3, diga "três", ou dizer "Atendimento ao cliente" para selecionar a opção mapeada para a tecla 3.</span><span class="sxs-lookup"><span data-stu-id="93419-228">If speech recognition is enabled, the name will automatically be recognized, and the person calling in will be able to either press 3, say "three," or say "Customer Service" to select the option mapped to key 3.</span></span>
- <span data-ttu-id="93419-229">Selecione onde a chamada será enviado se a tecla correspondente é pressionada, ou a opção está selecionada usando o reconhecimento de fala.</span><span class="sxs-lookup"><span data-stu-id="93419-229">Select where the call is to be sent if the corresponding key is pressed, or the option is selected using speech recognition.</span></span> <span data-ttu-id="93419-230">A chamada pode ser enviada para:</span><span class="sxs-lookup"><span data-stu-id="93419-230">The call can be sent to:</span></span>

  - <span data-ttu-id="93419-231">**Operador** Se operador já estiver configurado, ele é mapeado automaticamente a chave 0, mas ele também pode ser excluído ou reatribuído a uma chave diferente.</span><span class="sxs-lookup"><span data-stu-id="93419-231">**Operator** If operator is already set up, it is automatically mapped to key 0, but it can also be deleted or reassigned to a different key.</span></span> <span data-ttu-id="93419-232">If operator isn't set to any key, then the voice command "Operator" will be disabled too.</span><span class="sxs-lookup"><span data-stu-id="93419-232">If operator isn't set to any key, then the voice command "Operator" will be disabled too.</span></span>
  - <span data-ttu-id="93419-233">Uma **Pessoa da sua empresa** com uma licença de **Sistema de Telefonia** habilitada para Enterprise Voice ou com um Plano de Chamadas do Office 365 atribuído.</span><span class="sxs-lookup"><span data-stu-id="93419-233">A **Person in your company** with a **Phone System** license that is enabled for Enterprise Voice or assigned an Calling Plan in Office 365.</span></span> <span data-ttu-id="93419-234">Você pode configurá-lo para que o chamador possa ser enviado para a caixa postal.</span><span class="sxs-lookup"><span data-stu-id="93419-234">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="93419-235">Para fazer isso, selecione **a pessoa da sua empresa** e defina essa pessoa para que suas chamadas encaminhadas diretamente para a caixa postal.</span><span class="sxs-lookup"><span data-stu-id="93419-235">To do this, select **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span>

    > [!Note]
    > <span data-ttu-id="93419-236">A **Pessoa da sua empresa** pode ser um usuário Online ou um usuário hospedado no local usando o Skype for Business Server 2015 ou o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="93419-236">**Person in your company** can be an Online user or a user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013.</span></span> 
    - <span data-ttu-id="93419-237">Outro **atendedor automático**</span><span class="sxs-lookup"><span data-stu-id="93419-237">Another **Auto attendant**</span></span>

       <span data-ttu-id="93419-238">Você pode usar um atendedor automático existente para criar um segundo nível das opções de menu que contém um submenu.</span><span class="sxs-lookup"><span data-stu-id="93419-238">You can use an existing auto attendant to create a second level of menu options containing a sub-menu.</span></span> <span data-ttu-id="93419-239">These are called nested auto attendants.</span><span class="sxs-lookup"><span data-stu-id="93419-239">These are called nested auto attendants.</span></span> <span data-ttu-id="93419-240">Para enviar a chamada para um atendedor automático aninhados, selecione a **pessoa na empresa** e atribuir uma conta de recurso, um que já tenha um atendedor automático associado ou um que você irá associar a um atendedor automático depois que terminar criando este atendedor automático.</span><span class="sxs-lookup"><span data-stu-id="93419-240">To send the call to a nested auto attendant, select **Person in company** and assign a resource account, either one that already has an associated auto attendant or one that you will associate to an auto attendant once you are done creating this auto attendant.</span></span>

        > [!Note]
        > <span data-ttu-id="93419-241">O **horário comercial** de atendedores automáticos aninhados (ou segundo nível) também será usada, incluindo para as chamadas enviadas a partir de outros atendedores automáticos que foram configurados.</span><span class="sxs-lookup"><span data-stu-id="93419-241">The **Business Hours** of nested (or second-level) auto attendants will also be used, including for the calls sent from other auto attendants that have been set up.</span></span>

<!--    - **call queue** Using a call queue option allows the call to be transferred to an existing call queue that you have set up. -->

* * *

![Número 5](media/sfbcallout5.png)

<span data-ttu-id="93419-243">**Discagem por nome** Se você escolher essa opção, isso permitirá que as pessoas que ligam para pesquisar por pessoas em uma organização usando a pesquisa de diretório.</span><span class="sxs-lookup"><span data-stu-id="93419-243">**Dial by name** If you choose this option, this will enable people who call in to search for people in your organization using Directory Search.</span></span> <span data-ttu-id="93419-244">Você pode selecionar as pessoas que serão listadas como disponíveis ou indisponíveis para Discagem por Nome na página **Escopo de discagem**.</span><span class="sxs-lookup"><span data-stu-id="93419-244">You can select which people will be listed as available or not available for Dial by Name by setting up those options on the **Dial scope** page.</span></span> <span data-ttu-id="93419-245">Qualquer usuário online com uma licença de **Sistema de Telefonia** ou hospedado no local usando o Skype for Business Server 2015 ou o Lync Server 2013 pode ser encontrado com a Discagem por Nome.</span><span class="sxs-lookup"><span data-stu-id="93419-245">Any online user with a **Phone System** license, or any user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013, can be found with Dial by Name.</span></span>


* * *

<span data-ttu-id="93419-246">Quando você terminar com suas seleções, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="93419-246">When you are finished with your selections, click on **Next**.</span></span>

#### <a name="holiday-call-settings"></a><span data-ttu-id="93419-247">Configurações de chamada de feriado</span><span class="sxs-lookup"><span data-stu-id="93419-247">Holiday call settings</span></span>

<span data-ttu-id="93419-248">Você pode adicionar até 20 feriados agendados para cada atendedor automático.</span><span class="sxs-lookup"><span data-stu-id="93419-248">You can add up to 20 scheduled holidays to each auto attendant.</span></span>

> [!TIP]
> <span data-ttu-id="93419-249">Você pode passar a tela em **toda a organização configurações** > **feriados** para criar os feriados ou você pode criá-los como parte da criação de um novo manipulador de chamada.</span><span class="sxs-lookup"><span data-stu-id="93419-249">You can go the the screen at **Org-wide settings** > **Holidays** to create Holidays, or you can create them as part of creating a new call handler.</span></span>

![Configurar feriados no atendedor automático](media/50a5ce88-7f39-4210-808a-da7ced969854.png)

![Número 1](media/sfbcallout1.png)

<span data-ttu-id="93419-252">Se você já criou outros atendedores automáticos, você poderá ver uma opção que você pode usar ou editar no que você precisa dessa lista.</span><span class="sxs-lookup"><span data-stu-id="93419-252">If you've already created other auto attendants, you might see an option you can use or edit into what you need on this list.</span></span> <span data-ttu-id="93419-253">Caso contrário, você precisará criar um novo manipulador de chamada.</span><span class="sxs-lookup"><span data-stu-id="93419-253">If not, you'll need to create a new call handler.</span></span>

<span data-ttu-id="93419-254">Para adicionar um novo manipulador de chamada, clique em **+ novo manipulador de chamada**.</span><span class="sxs-lookup"><span data-stu-id="93419-254">To add a new call handler, click on **+ New call handler**.</span></span>

* * *

![Configurando feriados no atendedor automático da continuação](media/50a5ce88-7f39-4210-808a-da7ced969854b.png)

![Número 1](media/sfbcallout1.png)

<span data-ttu-id="93419-257">Na nova janela, insira um nome para seu novo manipulador de chamada na parte superior da tela.</span><span class="sxs-lookup"><span data-stu-id="93419-257">In the new window, enter a name for your new Call  handler at the top of the screen.</span></span>

![Número 2](media/sfbcallout2.png)

<span data-ttu-id="93419-259">Se o nome do seu evento já existir na lista suspensa **feriados** , você pode usá-lo.</span><span class="sxs-lookup"><span data-stu-id="93419-259">If the name of your holiday already exists in the **Holiday** pull-down list, you can use it.</span></span> <span data-ttu-id="93419-260">Se o nome do feriado que você precisa ainda não existir, selecione **Criar novo feriado** na lista suspensa e atribua um nome e uma data para o novo feriado na tela do novo que aparece.</span><span class="sxs-lookup"><span data-stu-id="93419-260">If the holiday name you need does not already exist, select **Create new holiday** in the pull-down list and assign a name and a date for the new holiday in the new screen that appears.</span></span> <span data-ttu-id="93419-261">Clique em **Salvar** quando estiver pronto.</span><span class="sxs-lookup"><span data-stu-id="93419-261">Click on **Save** when ready.</span></span>

<span data-ttu-id="93419-262">Os nomes de feriados podem ter até 64 caracteres e devem ser únicos para o mesmo atendedor automático.</span><span class="sxs-lookup"><span data-stu-id="93419-262">Holiday names may consist of up to 64 characters and must be unique for the same auto attendant.</span></span> <span data-ttu-id="93419-263">Por exemplo, você não pode ter dois feriados com o nome "Ação de Graças" no mesmo atendedor automático.</span><span class="sxs-lookup"><span data-stu-id="93419-263">For example, you cannot have two holidays named "Thanksgiving" in the same auto attendant.</span></span>

![Número 3](media/sfbcallout3.png)

<span data-ttu-id="93419-265">**Saudação** A saudação é opcional e pode ser definida como **Nenhuma saudação**.</span><span class="sxs-lookup"><span data-stu-id="93419-265">**Greeting** The greeting is optional and can be set to **No greeting**.</span></span> <span data-ttu-id="93419-266">Nesse caso, a pessoa que liga não ouvirá nenhuma mensagem ou saudação antes da chamada ser atendida por uma das opções selecionadas.</span><span class="sxs-lookup"><span data-stu-id="93419-266">In this case, the caller will hear no message or greeting before the call is handled by one of the options you select.</span></span> <span data-ttu-id="93419-267">Você também pode carregar um arquivo de áudio (em formatos .wav, .mp3 ou. wma) ou criar uma saudação personalizada usando conversão de texto em fala.</span><span class="sxs-lookup"><span data-stu-id="93419-267">You can also upload an audio file (in .wav, mp3 or .wma formats), or create a custom greeting using Text-to-Speech.</span></span>

- <span data-ttu-id="93419-268">**Nenhum saudação** Nenhum saudação será reproduzida quando as pessoas ligam para o número de telefone do atendedor automático.</span><span class="sxs-lookup"><span data-stu-id="93419-268">**No greeting** No greeting will be played when people call in to the auto attendant phone number.</span></span>
- <span data-ttu-id="93419-269">**Carregar um arquivo de áudio** Se você escolher essa opção, gravar a saudação de feriado e, em seguida, carregue o seu arquivo de áudio (em um formato. wav,. mp3 ou. wma)</span><span class="sxs-lookup"><span data-stu-id="93419-269">**Upload an audio file** If you choose this, record the holiday greeting and then upload your audio file (in a .wav, .mp3 or .wma format)</span></span>
- <span data-ttu-id="93419-270">**Digite uma mensagem de saudação** Se você escolher essa opção, insira o texto que você deseja que o sistema para ler (até 1000 caracteres).</span><span class="sxs-lookup"><span data-stu-id="93419-270">**Type a greeting message** If you choose this option, enter the text you want the system to read (up to 1000 characters).</span></span> <span data-ttu-id="93419-271">Por exemplo, você pode inserir "Feliz ano novo!</span><span class="sxs-lookup"><span data-stu-id="93419-271">For example, you might enter "Happy New Year!</span></span> <span data-ttu-id="93419-272">Nossos escritórios estão fechados no momento."</span><span class="sxs-lookup"><span data-stu-id="93419-272">Our offices are currently closed."</span></span> <span data-ttu-id="93419-273">Na caixa **Digite uma mensagem de saudação** .</span><span class="sxs-lookup"><span data-stu-id="93419-273">in the **Type a greeting message** box.</span></span>

![Número 4](media/sfbcallout4.png)

<span data-ttu-id="93419-275">**Ações** Você pode selecionar o que acontece com as chamadas que chegam durante este feriado.</span><span class="sxs-lookup"><span data-stu-id="93419-275">**Actions** You can select what happens to the calls that arrive during this holiday.</span></span> <span data-ttu-id="93419-276">Você pode escolher entre as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="93419-276">You can chose from the following options:</span></span>

- <span data-ttu-id="93419-277">**Desconectar** A pessoa será desconectada após ouvir a saudação de feriado.</span><span class="sxs-lookup"><span data-stu-id="93419-277">**Disconnect** The person calling in will be disconnected after hearing the holiday greeting.</span></span>
- <span data-ttu-id="93419-278">**Redirecionar chamada** Isso pode ser usado para enviar a chamada automaticamente para:</span><span class="sxs-lookup"><span data-stu-id="93419-278">**Redirect call** This can be used to automatically send the call to:</span></span>
  - <span data-ttu-id="93419-279">Uma **Pessoa da sua empresa** com uma licença de **Sistema de Telefonia** habilitada para Enterprise Voice ou com Planos de Chamadas do Office 365 atribuídos.</span><span class="sxs-lookup"><span data-stu-id="93419-279">A **Person in your company** with a **Phone System** license that is enabled for Enterprise Voice or assigned Calling Plans in Office 365.</span></span> <span data-ttu-id="93419-280">Você pode configurá-lo para que o chamador possa ser enviado para a caixa postal.</span><span class="sxs-lookup"><span data-stu-id="93419-280">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="93419-281">Para fazer isso, selecione a **pessoa na sua empresa**e defina essa pessoa para que suas chamadas encaminhadas diretamente para a caixa postal.</span><span class="sxs-lookup"><span data-stu-id="93419-281">To do this, select **Person in your company**, and set this person to have their calls forwarded directly to voicemail.</span></span>

    > [!Note]
    > <span data-ttu-id="93419-282">A **Pessoa da sua empresa** pode ser um usuário Online ou um usuário hospedado no local usando o Skype for Business Server 2015 ou o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="93419-282">**Person in your company** can be an Online user or a user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013.</span></span> 

  - <span data-ttu-id="93419-283">Uma **fila de chamadas** para transferir a chamada para uma fila de chamada existente que você definiu.</span><span class="sxs-lookup"><span data-stu-id="93419-283">A **call queue** to transfer the call to an existing call queue that you have set up.</span></span>
  - <span data-ttu-id="93419-284">Outro **atendedor automático**, para criar um segundo nível das opções de menu que contém um submenu.</span><span class="sxs-lookup"><span data-stu-id="93419-284">Another **Auto attendant**, to create a second level of menu options containing a sub-menu.</span></span> <span data-ttu-id="93419-285">These are called nested auto attendants.</span><span class="sxs-lookup"><span data-stu-id="93419-285">These are called nested auto attendants.</span></span>

    > [!Note]
    > <span data-ttu-id="93419-286">Por padrão, todas as chamadas recebidas durante um período de feriado desconectam a pessoa após a saudação (se houver uma), portanto, você deve especificar um redirecionamento caso outro comportamento seja desejado.</span><span class="sxs-lookup"><span data-stu-id="93419-286">By default, all calls arriving during a holiday period are set to disconnect after the greeting (if any), so you must specify a redirect if a different behavior is desired.</span></span>

#### <a name="select-dial-scope-page"></a><span data-ttu-id="93419-287">Página Selecionar escopo de discagem</span><span class="sxs-lookup"><span data-stu-id="93419-287">Select dial scope page</span></span>

<span data-ttu-id="93419-288">Nesta página, você pode configurar quais usuários em sua organização poderão ser listados no diretório e disponíveis para discagem pelo nome quando uma pessoa que chama em sua organização.</span><span class="sxs-lookup"><span data-stu-id="93419-288">On this page, you can set up which users in your organization will be listed in your directory and available for Dial by Name when a person that calls in to your organization.</span></span>

![Dial scope for searching with dial by name.](media/1bcb185c-00db-43a7-b5c4-9b021c0627f7.png)

* * *

<span data-ttu-id="93419-290">![Número 1](media/sfbcallout1.png) usando a opção **incluir** , você tem duas opções:</span><span class="sxs-lookup"><span data-stu-id="93419-290">![Number 1](media/sfbcallout1.png) Using the **Include** option, you have two options:</span></span>

- <span data-ttu-id="93419-291">**Todos os usuários online** O uso dessa opção permite que todas as pessoas da organização sejam incluídas na pesquisa do diretório.</span><span class="sxs-lookup"><span data-stu-id="93419-291">**All Online users** Using this option allows all of the people in your organization to be included in directory search.</span></span> <span data-ttu-id="93419-292">Todos os usuários Online com uma licença de **Sistema de Telefonia**, bem como os usuários hospedados no local que usam o Skype for Business Server 2015 ou o Lync Server 2013, que têm Planos de Chamadas no Office 365, serão listados.</span><span class="sxs-lookup"><span data-stu-id="93419-292">All Online users with a **Phone System** license, as well as users hosted on-premises using Skype for Business Server 2015 or Lync Server 2013 who have Calling Plans in Office 365, will be listed.</span></span>
- <span data-ttu-id="93419-293">**Grupo de usuário personalizado** Se você usar essa opção, você pode procurar um grupo do Office 365, lista de distribuição ou grupo de segurança que foi criado em sua organização e as pessoas adicionadas para este grupo do Office 365, lista de distribuição ou grupo de segurança que são um dos **usuários Online com uma Licença do sistema telefônico** ou hospedado no local usando Skype para Business Server 2015 ou o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="93419-293">**Custom user group** If you use this option, you can search for an Office 365 Group, distribution list, or security group that has been created in your organization, and the people added to this Office 365 Group, distribution list, or security group who are either **Online users with a Phone System license** or hosted on-premises using Skype for Business Server 2015 or Lync Server 2013.</span></span> <span data-ttu-id="93419-294">Você pode adicionar vários grupos do Office 365, listas de distribuição e grupos de segurança.</span><span class="sxs-lookup"><span data-stu-id="93419-294">You can add multiple Office 365 Groups, distribution lists, and security groups.</span></span>

* * *

![Número 2](media/sfbcallout2.png)

<span data-ttu-id="93419-296">Usando a opção **Excluir** , você tem duas opções:</span><span class="sxs-lookup"><span data-stu-id="93419-296">Using the **Exclude** option, you have two options:</span></span>

- <span data-ttu-id="93419-297">**Nenhuma** O uso desta opção indicará que nenhum usuário online será excluído da pesquisa de diretório.</span><span class="sxs-lookup"><span data-stu-id="93419-297">**None** Using this option will indicate that no Online users will be excluded from directory search.</span></span>
- <span data-ttu-id="93419-298">**Grupo de usuário personalizado** Se você usar essa opção, você pode procurar um grupo do Office 365, lista de distribuição ou grupo de segurança que foi criado em sua organização, e todas as pessoas adicionado a esse grupo do Office 365, lista de distribuição ou grupos de segurança serão excluídos da pesquisa de diretório.</span><span class="sxs-lookup"><span data-stu-id="93419-298">**Custom user group** If you use this option, you can search for an Office 365 Group, distribution list, or security group that has been created in your organization, and all people added to this Office 365 Group, distribution list, or security groups will be excluded from directory search.</span></span> <span data-ttu-id="93419-299">Você pode adicionar vários grupos do Office 365, listas de distribuição e grupos de segurança.</span><span class="sxs-lookup"><span data-stu-id="93419-299">You can add multiple Office 365 Groups, distribution lists, and security groups.</span></span>

> [!NOTE]
> <span data-ttu-id="93419-300">Poderá demorar até 36 horas para um novo usuário ter seu nome listado no diretório quando alguém usa discagem pelo nome, com reconhecimento de fala.</span><span class="sxs-lookup"><span data-stu-id="93419-300">It might take up to 36 hours for a new user to have their name listed in the directory when someone uses Dial by Name with speech recognition.</span></span>

<span data-ttu-id="93419-301">Depois de inserir todos os campos necessários e configurar opções e menus de tratamento de chamada, clique em **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="93419-301">After you enter all the required fields and set up call handling menus and options, click **Submit**.</span></span>

## <a name="editing-and-testing-auto-attendants"></a><span data-ttu-id="93419-302">Edição e testes atendedores automáticos</span><span class="sxs-lookup"><span data-stu-id="93419-302">Editing and testing auto attendants</span></span>

<span data-ttu-id="93419-303">Depois de ter salvo o atendedor automático, ele será listado na página **Atendedores automáticos**.</span><span class="sxs-lookup"><span data-stu-id="93419-303">After you have saved your auto attendant, it will be listed on the **Auto attendants** page.</span></span> <span data-ttu-id="93419-304">Isso permitirá que você veja rapidamente algumas das opções que você definiu, incluindo o nome, número de telefone, idioma e status.</span><span class="sxs-lookup"><span data-stu-id="93419-304">This will allow you to quickly see some of the options that you have set up, including the name, phone number, language, and status.</span></span>

<span data-ttu-id="93419-305">Se desejar fazer alterações em um atendedor automático, selecione o atendedor automático e, em seguida, no painel de ações, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="93419-305">If you want to make changes to an auto attendant, select the auto attendant, and then in the Action pane click **Edit**.</span></span>

<span data-ttu-id="93419-306">Também rapidamente, você pode colocar uma chamada de teste para o atendedor automático usando o botão **Testar** no painel ação.</span><span class="sxs-lookup"><span data-stu-id="93419-306">You can also quickly place a test call to your auto attendant by using the **Test** button in the Action pane.</span></span>

## <a name="want-to-know-more"></a><span data-ttu-id="93419-307">Deseja saber mais?</span><span class="sxs-lookup"><span data-stu-id="93419-307">Want to know more?</span></span>

<span data-ttu-id="93419-308">Você também pode usar o Windows PowerShell para criar e configurar atendedores automáticos.</span><span class="sxs-lookup"><span data-stu-id="93419-308">You can also use Windows PowerShell to create and set up auto attendants.</span></span>

### <a name="auto-attendant-cmdlets"></a><span data-ttu-id="93419-309">Cmdlets de atendedores automáticos</span><span class="sxs-lookup"><span data-stu-id="93419-309">Auto attendant cmdlets</span></span>

<span data-ttu-id="93419-310">Veja os cmdlets necessários para gerenciar um atendedor automático.</span><span class="sxs-lookup"><span data-stu-id="93419-310">Here are the cmdlets that you need to manage an auto attendant.</span></span>

- [<span data-ttu-id="93419-311">New-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="93419-311">New-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant?view=skype-ps)  
- [<span data-ttu-id="93419-312">Set-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="93419-312">Set-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csautoattendant?view=skype-ps) 
- [<span data-ttu-id="93419-313">Get-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="93419-313">Get-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csattendant?view=skype-ps) 
- [<span data-ttu-id="93419-314">Get-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="93419-314">Get-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csautoattendantholidays?view=skype-ps) 
- [<span data-ttu-id="93419-315">Remove-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="93419-315">Remove-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csautoattendant?view=skype-ps) 
- [<span data-ttu-id="93419-316">New-CsAutoAttendantMenu</span><span class="sxs-lookup"><span data-stu-id="93419-316">New-CsAutoAttendantMenu</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendantmenu?view=skype-ps) 
- [<span data-ttu-id="93419-317">New-CsOnlineAudioFile</span><span class="sxs-lookup"><span data-stu-id="93419-317">New-CsOnlineAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineAudioFile?view=skype-ps) 
- [<span data-ttu-id="93419-318">New-CsAutoAttendantCallFlow</span><span class="sxs-lookup"><span data-stu-id="93419-318">New-CsAutoAttendantCallFlow</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallFlow?view=skype-ps) 
- [<span data-ttu-id="93419-319">Export-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="93419-319">Export-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/export-Export-CsAutoAttendantHolidays?view=skype-ps) 
- [<span data-ttu-id="93419-320">New-CsOnlineTimeRange</span><span class="sxs-lookup"><span data-stu-id="93419-320">New-CsOnlineTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-New-CsOnlineTimeRange?view=skype-ps) 
- [<span data-ttu-id="93419-321">New-CsOnlineDateTimeRange</span><span class="sxs-lookup"><span data-stu-id="93419-321">New-CsOnlineDateTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinedatetimerange?view=skype-ps) 
- [<span data-ttu-id="93419-322">New-CsOnlineSchedule</span><span class="sxs-lookup"><span data-stu-id="93419-322">New-CsOnlineSchedule</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsOnlineSchedule?view=skype-ps) 
- [<span data-ttu-id="93419-323">Get-CsAutoAttendantSupportedTimeZone</span><span class="sxs-lookup"><span data-stu-id="93419-323">Get-CsAutoAttendantSupportedTimeZone</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone?view=skype-ps)
- [<span data-ttu-id="93419-324">New-CsAutoAttendantCallHandlingAssociation</span><span class="sxs-lookup"><span data-stu-id="93419-324">New-CsAutoAttendantCallHandlingAssociation</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation?view=skype-ps)
- [<span data-ttu-id="93419-325">Get-CsAutoAttendantSupportedLanguage</span><span class="sxs-lookup"><span data-stu-id="93419-325">Get-CsAutoAttendantSupportedLanguage</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage?view=skype-ps)
- [<span data-ttu-id="93419-326">Import-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="93419-326">Import-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csautoattendantholidays?view=skype-ps) 
- [<span data-ttu-id="93419-327">New-CsAutoAttendantCallableEntity</span><span class="sxs-lookup"><span data-stu-id="93419-327">New-CsAutoAttendantCallableEntity</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallableEntity?view=skype-ps) 

### <a name="more-about-windows-powershell"></a><span data-ttu-id="93419-328">Mais sobre o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="93419-328">More about Windows PowerShell</span></span>

- <span data-ttu-id="93419-329">O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer.</span><span class="sxs-lookup"><span data-stu-id="93419-329">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="93419-330">Com o Windows PowerShell, você pode gerenciar o Office 365 e Microsoft Teams usando um único ponto de administração que pode simplificar o seu trabalho diário, quando você tem várias tarefas fazer.</span><span class="sxs-lookup"><span data-stu-id="93419-330">With Windows PowerShell, you can manage Office 365 and Microsoft Teams using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="93419-331">Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="93419-331">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="93419-332">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="93419-332">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [<span data-ttu-id="93419-333">Por que você precisa usar o PowerShell do Office 365</span><span class="sxs-lookup"><span data-stu-id="93419-333">Why you need to use Office 365 PowerShell</span></span>](https://docs.microsoft.com/en-us/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- <span data-ttu-id="93419-334">Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade apenas usando o Centro de administração do Microsoft 365, como quando você estiver fazendo alterações de configuração de muitos usuários de uma só vez.</span><span class="sxs-lookup"><span data-stu-id="93419-334">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="93419-335">Saiba mais sobre essas vantagens nos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="93419-335">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="93419-336">Gerenciar o Office 365 com o Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="93419-336">Manage Office 365 with Office 365 PowerShell</span></span>](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [<span data-ttu-id="93419-337">Usar o Windows PowerShell para gerenciar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="93419-337">Using Windows PowerShell to manage Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a><span data-ttu-id="93419-338">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="93419-338">Related topics</span></span>

[<span data-ttu-id="93419-339">Veja aqui o que você obtém com o Sistema de Telefonia no Office 365</span><span class="sxs-lookup"><span data-stu-id="93419-339">Here's what you get with Phone System in Office 365</span></span>](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[<span data-ttu-id="93419-340">Obter números de telefone de serviço</span><span class="sxs-lookup"><span data-stu-id="93419-340">Getting service phone numbers</span></span>](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)

[<span data-ttu-id="93419-341">Disponibilidade de audioconferência e planos de chamadas por país e região</span><span class="sxs-lookup"><span data-stu-id="93419-341">Country and region availability for Audio Conferencing and Calling Plans</span></span>](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

[<span data-ttu-id="93419-342">New-CsOrganizationalAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="93419-342">New-CsOrganizationalAutoAttendant</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/new-csorganizationalautoattendant?view=skype-ps)  

[<span data-ttu-id="93419-343">Quais são os atendedores automáticos do Cloud?</span><span class="sxs-lookup"><span data-stu-id="93419-343">What are Cloud auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)

[<span data-ttu-id="93419-344">Exemplo de pequenas empresas - Configurar um atendedor automático</span><span class="sxs-lookup"><span data-stu-id="93419-344">Small business example - Set up an auto attendant</span></span>](https://docs.microsoft.com/skypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa)  
