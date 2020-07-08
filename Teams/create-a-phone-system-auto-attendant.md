---
title: Configurar um atendedor automático do Cloud
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: waseemh
ms.topic: article
ms.assetid: 6fc2687c-0abf-43b8-aa54-7c3b2a84b67c
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
description: Saiba como configurar e testar atendedores automáticos da nuvem para o Microsoft Teams.
ms.openlocfilehash: 247cb553c2fb3c4dafd1a36b826fc13f2f21b0ce
ms.sourcegitcommit: c8b5d4dd70d183f7ca480fb735a19290a3457b30
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/08/2020
ms.locfileid: "45077707"
---
# <a name="set-up-a-cloud-auto-attendant"></a>Configurar um atendedor automático do Cloud

Os atendedores automáticos permitem que as pessoas liguem para sua organização e naveguem em um sistema de menus para falar com o departamento certo, a fila de chamadas, a pessoa ou um operador. Você pode criar atendedores automáticos para sua organização com o centro de administração do Microsoft Teams ou com o PowerShell. Para criar um atendedor automático, vá para **voz** no painel de navegação esquerdo e, em seguida, selecione **atendedores automáticos**  >  **Adicionar novo**.

Se você quiser saber mais sobre atendedores automáticos, consulte [o que são atendedores automáticos da nuvem?](/microsoftteams/what-are-phone-system-auto-attendants)

> [!NOTE]
> Este artigo se aplica ao Microsoft Teams e ao Skype for Business online.

Os números de telefone não são atribuídos diretamente ao atendedor automático, mas a uma [conta de recurso](manage-resource-accounts.md) associada ao atendedor automático.

As implementações de atendedor automático geralmente envolvem vários atendedores automáticos. Um atendedor automático de *primeiro nível* geralmente tem uma conta de recurso com um número de telefone atribuído. Um atendedor automático aninhado é usado como um menu de segundo nível ao qual o atendedor automático de *primeiro nível* se conecta como chamada para. Um atendedor automático *aninhado* não é necessário para ter um número de telefone atribuído à sua conta de recurso.

## <a name="step-1--get-started"></a>Etapa 1-Introdução

Um atendedor automático é necessário para ter uma conta de recurso associada. Consulte [gerenciar contas de recursos no Teams](manage-resource-accounts.md) para obter detalhes sobre contas de recursos e todas as licenças necessárias. 
 
<!-- When you create a new auto attendant in Teams after October 10th, 2019, the required auto attendant is automatically created and linked with the new auto attendant. -->
 
> [!TIP]
> Para redirecionar chamadas para um operador ou uma opção de menu que seja um usuário online com uma licença do sistema de telefonia, será necessário habilitá-las para o Enterprise Voice. Consulte [atribuir licenças do Skype for Business](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) ou [atribuir licenças do suplemento do Microsoft Teams](teams-add-on-licensing/assign-teams-add-on-licenses.md). Você também pode usar o Windows PowerShell. Por exemplo, execute:`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

## <a name="step-2--create-auto-attendants"></a>Etapa 2 — criar atendedores automáticos

> [!IMPORTANT]
> Cada atendedor automático é necessário para ter uma [conta de recurso](manage-resource-accounts.md)associada. Você deve criar a conta do recurso primeiro, então você pode associá-la ao atendedor automático.

### <a name="with-the-microsoft-teams-admin-center"></a>Com o centro de administração do Microsoft Teams

No **centro de administração do Microsoft Teams**, clique em **Voice**  >  **atendedores automáticos**de voz e, em seguida, clique em **+ Adicionar**:

#### <a name="general-info-page"></a>Página de informações gerais

![Captura de tela da página meu atendedor automático](media/edacec94-9384-4a87-be0a-5c49a151287e.png)

* * *

![Ícone do número 1, um texto explicativo no nome anterior da captura de tela ](media/teamscallout1.png)
 **Name** Insira um nome de exibição para o atendedor automático. O nome é obrigatório e pode conter até 64 caracteres, incluindo espaços. O **nome** que você designar aqui estará listado em uma coluna na guia **atendedores automáticos** .

<a name="phonenumber"> </a>

* * *

![Ícone do número 2, um balão no operador de captura de tela ](media/teamscallout2.png)
 <a name="operator"> </a>anterior 
 **Operator** é opcional (mas recomendado). Você pode definir a opção de **operador** para permitir que os chamadores quebrem nos menus e falar com uma pessoa designada.

A tecla 0 é atribuída ao operador por padrão.

Se você definir um operador, solicite às pessoas que chamam sobre a opção nas **Opções do menu Editar** na página **fluxo de chamadas** . Se você definir um operador em seu atendedor automático, insira o texto de aviso correspondente na caixa **chamadores ouvirá** ou altere o arquivo de áudio para incluir essa opção. Por exemplo, "Para falar com o operador, pressione 0".

Você tem várias maneiras de definir o operador:

- **Nenhum operador** desabilita as opções "operador" e "pressionar 0". Este é o padrão atual.
- **Pessoa na organização** atribui uma pessoa com uma licença do sistema de telefonia habilitada para Enterprise Voice ou planos de chamada atribuídos no Microsoft 365 ou no Office 365. Você também pode configurá-lo para que o chamador seja enviado ao correio de voz. Para enviar um chamador para correio de voz, selecione **pessoa na organização** e defina as configurações da conta para enviar chamadas diretamente para o correio de voz.

     > [!Note]
     > A **pessoa na organização** pode ser um usuário online ou um usuário hospedado no local usando o Skype for Business Server. Ao selecionar **pessoa na organização** , você pode selecionar uma conta com uma caixa de correio compartilhada ou com uma caixa de correio do usuário.

- **Aplicativo de voz**  Selecione o nome da conta de recurso vinculada a um atendedor automático ou fila de chamadas que já foi criada. Os chamadores que solicitam um operador são redirecionados para lá.
- **Número de telefone externo** transfere o chamador para um número de telefone externo que você especificar. Observe o seguinte:

    - A conta do recurso associada ao aplicativo que faz a transferência PSTN deve ter um número de telefone e receber uma licença do sistema de telefonia virtual. Não há suporte para licenças do sistema telefônico. Além disso, a conta do recurso deve ter um dos seguintes:
        - Para uma conta de recurso com um número de plano de chamada, atribua uma licença de [plano de chamada](calling-plans-for-office-365.md) .
        - Para uma conta de recurso com um número de roteamento direto, atribua uma [política de roteamento de voz online](manage-voice-routing-policies.md).
    - O número de telefone de saída exibido é determinado da seguinte maneira:
        - Para números de plano de chamada, o número de telefone do chamador original é exibido.
        - Para números de roteamento direto, o número enviado é baseado na configuração P-Assertd-Identity (PAI) no SBC, da seguinte maneira:
            - Se definido como Disabled, o número de telefone do chamador original será exibido. Esta é a configuração padrão e recomendada.
            - Se definido como habilitado, o número de telefone da conta do recurso será exibido.
    - Não há suporte para transferências entre troncos de plano de chamada e troncos diretos de roteamento.

<!--   

- **Auto attendant** Select the name of the resource account linked to an auto attendant that has already been created. Callers that request an operator are redirected there.
- **Call queue** Select the name of the resource account linked to a call queue that has already been created. Callers that request an operator are redirected there.

**Phone number (optional)** Enter the service phone number you want to assign to the new resource account this wizard creates and links to the new auto attendant. If you intend this auto attendant to be a nested auto attendant, it doesn't need a phone number. You can add one if for some reason you require several ways to connect to the auto attendant system.

> [!NOTE]
> Auto attendants created after October 10th, 2019 also create a new [resource account](manage-resource-accounts.md) that is associated with the auto attendant. If a phone number is applied to the auto attendant's resource account,  a Phone System - Virtual user license is applied to the resource account if one is available.
-->

* * *

<a name="timezone"> </a>

![Ícone do número 3, um texto explicativo no fuso horário anterior da captura de tela, ](media/teamscallout3.png) **Time zone** você precisa definir o fuso horário para o atendedor automático. A configuração pode ser a mesma que o fuso horário do endereço principal listado para a sua organização ou um fuso horário diferente. Cada atendedor automático pode ter um fuso horário diferente. O horário comercial definido para o atendedor automático também usa este fuso horário. Certifique-se de definir o fuso horário certo para evitar discrepâncias de horário comercial, pois nem todas as regiões têm o horário de verão. 

* * *

![Ícone do número 4, um texto explicativo no idioma anterior da captura de tela ](media/teamscallout4.png)
 <a name="language"> </a>, 
 **Language** selecione o idioma que você deseja usar para o atendedor automático. O atendedor automático usa esse idioma com chamadores e todos os prompts do sistema são reproduzidos nesse idioma.

 * * *

![Ícone do número 5, um texto explicativo na captura de tela anterior ](media/teamscallout5.png)
 **habilitar** o reconhecimento de fala de entrada de voz estará disponível se essa opção estiver selecionada. Os chamadores podem usar a entrada de voz no [idioma que você definir](set-auto-attendant-languages-for-audio-conferencing-in-teams.md). Se quiser permitir que as pessoas usem o teclado numérico do telefone para fazer seleções, você pode deixar o reconhecimento de fala definido como **desativado**.

* * *  

Quando terminar de selecionar as opções, clique em **Avançar**.

#### <a name="call-flow"></a>Fluxo de chamadas

<a name="greetingsandrouting"> </a>

> [!TIP]
> Você pode optar por configurar um plano de horário comercial personalizado, com diferentes comportamentos de fluxo de chamada durante e após o horário comercial. Para definir um cronograma personalizado, defina o [fluxo de chamadas opcional para horas](#call-flow-for-after-hours)extras. Por padrão, um atendedor automático usa fluxos de chamadas do horário comercial.

Você pode configurar saudações, avisos e menus personalizados que as pessoas ouvem quando chegam ao atendedor automático.

![Captura de tela: seção saudação da página de manipulação de chamadas](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)

* * *

**Primeiro, reproduza uma mensagem de saudação** Uma saudação é opcional e pode ser definida como **sem saudação**, **executar um arquivo de áudio**ou **digitar uma mensagem de saudação**.

> [!NOTE]
> Uma saudação é mais valiosa para um atendedor automático de primeiro nível. Geralmente, um atendedor automático aninhado não precisa de uma saudação.

![Ícone do número 1, um texto explicativo na captura de tela anterior ](media/teamscallout1.png) se você **não selecionar nenhuma saudação**, o chamador não ouvirá uma mensagem ou saudação antes que a chamada seja manipulada por uma das ações que você selecionar mais tarde. 

<!-- You can also upload an audio file (in .wav, mp3 or .wma formats), or create a custom greeting using Text-to-Speech.-->

![Ícone do número 2, um texto explicativo na captura de tela anterior ](media/teamscallout2.png) se você selecionar **executar um arquivo de áudio** , poderá usar o botão **carregar arquivo** para carregar uma mensagem de saudação gravada salva como áudio. WAV,. MP3 ou. Formato WMA. A gravação não pode ter mais de 5 MB.

![Ícone do número 3, um texto explicativo na captura de tela anterior ](media/teamscallout3.png) **digite uma mensagem de saudação** , se você escolher essa opção, insira o texto que você deseja que o sistema leia (até 1000 caracteres) no campo fornecido. Por exemplo, digite "bem-vindo à contoso. A sua ligação é muito importante para nós." A saída é criada pelo software de texto para voz.

* * *

Você pode selecionar o que acontece ao lado de chamadas das seguintes ações na seção **encaminhar a chamada** . As configurações são **Opções de menu** **Desconectar**, **chamada redirecionar**ou reproduzir.

Se você selecionar **Desconectar**, o chamador será desconectado após a saudação ser reproduzida. 

<a name="redirectcalls"> </a>

![Ícone do número 4, um texto explicativo na chamada de ](media/teamscallout4.png) **redirecionamento** de captura de tela anterior envia o chamador para o destino escolhido sem escolher entre as opções. As configurações possíveis são:

  - **Pessoa na organização** A conta que você escolher deve ter uma licença do sistema de telefonia habilitada para Enterprise Voice ou ter um plano de chamada atribuído no Microsoft 365 ou no Office 365. Você pode configurá-lo para que o chamador possa ser enviado para o correio de voz. Selecione **pessoa na organização** e defina essa conta para fazer com que as chamadas sejam encaminhadas diretamente para o correio de voz.

    > [!Note]
    > A **pessoa na organização** pode ser um usuário online ou um usuário hospedado no local usando o Skype for Business Server. Ao selecionar **pessoa na organização** , você pode selecionar uma conta com uma caixa de correio compartilhada ou com uma caixa de correio do usuário.

  - **Aplicativo de voz** Selecione um atendedor automático ou fila de chamadas que já tenha sido configurada. Você pesquisa o atendedor automático ou a fila de chamadas pelo nome da conta do recurso associada ao serviço.
  - **Número de telefone externo** transfere o chamador para um número de telefone externo que você especificar. Observe o seguinte:

    - A conta do recurso associada ao aplicativo que faz a transferência PSTN deve ter um número de telefone e receber uma licença do sistema de telefonia virtual. Não há suporte para licenças do sistema telefônico. Além disso, a conta do recurso deve ter um dos seguintes:
        - Para uma conta de recurso com um número de plano de chamada, atribua uma licença de [plano de chamada](calling-plans-for-office-365.md) .
        - Para uma conta de recurso com um número de roteamento direto, atribua uma [política de roteamento de voz online](manage-voice-routing-policies.md).
    - O número de telefone de saída exibido é determinado da seguinte maneira:
        - Para números de plano de chamada, o número de telefone do chamador original é exibido.
        - Para números de roteamento direto, o número enviado é baseado na configuração P-Assertd-Identity (PAI) no SBC, da seguinte maneira:
            - Se definido como Disabled, o número de telefone do chamador original será exibido. Esta é a configuração padrão e recomendada.
            - Se definido como habilitado, o número de telefone da conta do recurso será exibido.
    - Não há suporte para transferências entre troncos de plano de chamada e troncos diretos de roteamento.
  - **Correio de voz** Selecione o grupo do Microsoft 365 que contém os usuários em sua organização que precisam acessar o correio de voz recebido por este atendedor automático. As mensagens de correio de voz são enviadas para o grupo do Microsoft 365 que você especificou. Para acessar mensagens de correio de voz, os membros do grupo podem abri-los navegando para o grupo no Outlook.

      Alterne a **transcrição** para **ativado** para habilitar a transcrição de voz para texto de mensagens de correio de voz.


 * * *

![Captura de tela: seção ações da página de manipulação de chamadas](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8b.png)

![Ícone do número 1, um texto explicativo na captura de tela anterior ](media/teamscallout1.png) ao selecionar **Opções do menu reproduzir** , você pode selecionar se deseja usar um arquivo de áudio ou inserir texto que será renderizado como texto para fala para dar opções de menu de discagem aos chamadores. Selecione esta opção em vez das opções de **chamada de redirecionamento para** ou **Desconectar** .


![Ícone do número 2, um texto explicativo na captura de tela anterior ](media/teamscallout2.png) **reproduz um arquivo de áudio** permite que você configure um prompt e opções para o chamador escolher. 
- Se você selecionar **executar um arquivo de áudio** , poderá usar o botão **carregar arquivo** para carregar uma mensagem de saudação gravada salva como áudio. WAV,. MP3 ou. Formato WMA. A gravação não pode ter mais de 5 MB.

- **Digite uma mensagem de saudação** Se você escolher essa opção, insira o texto que deseja que o sistema Leia (até 1000 caracteres) no campo fornecido. Por exemplo, digite "bem-vindo à contoso. A sua ligação é muito importante para nós." A saída é criada pelo software de texto para voz.

**Definir opções de menu** O teclado do telefone ou os comandos de voz podem ser adicionados ou removidos nesta caixa de diálogo. Para excluir uma opção de menu, remova a entrada de comando de voz e defina **redirecionamento** para de volta para **selecionar**.

> [!TIP]
> Atualize o texto do prompt do menu ou regrave os prompts de áudio quando remover as opções. O prompt de menu reproduzido para chamadores não é atualizado automaticamente.  
>
> Qualquer opção de menu pode ser adicionada e removida em qualquer ordem, e os mapeamentos de chave não precisam ser contínuos. É possível, por exemplo, criar um menu com as teclas 0, 1 e 3 mapeadas para as opções, enquanto a tecla 2 não é usada.

> [!NOTE]
> As chaves \* (repetir) e \# (verso) são reservadas pelo sistema e não podem ser reatribuídas. Se o reconhecimento de fala estiver habilitado, pressionar * corresponderá com "repetir" e # corresponderá com os comandos de voz "verso".

![Ícone do número 3, um texto explicativo na captura de tela anterior ](media/teamscallout3.png) para configurar uma opção de menu, clique na **tecla + atribuir uma tecla de discagem** e insira as informações das seguintes opções:

![O ícone do número 4, um texto explicativo na coluna anterior de ](media/teamscallout4.png) **comando de voz** de captura de tela de uma opção pode ter até 64 caracteres de comprimento e pode conter várias palavras como "atendimento ao cliente" ou "operações e aterramento".   Se o reconhecimento de fala estiver habilitado, o nome será reconhecido automaticamente, e o autor será capaz de pressionar 3, diga "três" ou diga "atendimento ao cliente" para selecionar a opção mapeada para a chave 3. Esse texto também é renderizado por texto em fala para o prompt de confirmação do serviço, que pode ser algo parecido com "Transferindo sua chamada para a operadora".

![Ícone do número 5, um texto explicativo na captura de tela anterior, ](media/teamscallout5.png) a opção **redirecionar para** define o local em que a chamada vai se a tecla correspondente for pressionada ou a opção for selecionada usando o reconhecimento de fala. A chamada pode ser enviada para:

<!-- Is the Operator behavior changing here? Looks like operator is only an available option for dial key 0 -->

- **Operador** de Se um operador já estiver configurado, a opção será automaticamente mapeada para a chave 0, mas também pode ser excluída ou reatribuída a uma chave diferente. O chamador que seleciona essa opção é enviado para o operador designado. Se o operador não estiver definido como qualquer chave, o comando de voz "operador" também será desabilitado. 
- A **pessoa na organização** pode ser um usuário online ou um usuário hospedado no local usando o Skype for Business Server. O usuário deve ter uma licença de sistema telefônico habilitada para Enterprise Voice ou planos de chamada atribuídos no Microsoft 365 ou no Office 365. Procure a pessoa no campo **Pesquisar por nome** .

- **Aplicativo de voz** Selecione um atendedor automático ou fila de chamadas que já tenha sido configurada. Você pesquisa o atendedor automático ou a fila de chamadas pelo nome da conta de recurso associada ao aplicativo.

- **Número de telefone externo** transfere o chamador para um número de telefone externo que você especificar. Observe o seguinte:

    - A conta do recurso associada ao aplicativo que faz a transferência PSTN deve ter um número de telefone e receber uma licença do sistema de telefonia virtual. Não há suporte para licenças do sistema telefônico. Além disso, a conta do recurso deve ter um dos seguintes:
        - Para uma conta de recurso com um número de plano de chamada, atribua uma licença de [plano de chamada](calling-plans-for-office-365.md) .
        - Para uma conta de recurso com um número de roteamento direto, atribua uma [política de roteamento de voz online](manage-voice-routing-policies.md).
    - O número de telefone de saída exibido é determinado da seguinte maneira:
        - Para números de plano de chamada, o número de telefone do chamador original é exibido.
        - Para números de roteamento direto, o número enviado é baseado na configuração P-Assertd-Identity (PAI) no SBC, da seguinte maneira:
            - Se definido como Disabled, o número de telefone do chamador original será exibido. Esta é a configuração padrão e recomendada.
            - Se definido como habilitado, o número de telefone da conta do recurso será exibido.
    - Não há suporte para transferências entre troncos de plano de chamada e troncos diretos de roteamento.

- **Correio de voz** Selecione o grupo do Microsoft 365 que contém os usuários em sua organização que precisam acessar o correio de voz recebido por este atendedor automático. As mensagens de correio de voz são enviadas para o grupo do Microsoft 365 que você especificou. Para acessar mensagens de correio de voz, os membros do grupo podem abri-los navegando para o grupo no Outlook.

    Alterne a **transcrição** para **ativado** para habilitar a transcrição de voz para texto de mensagens de correio de voz.

<!-- - **Auto attendant** Select the name of an existing auto attendant in the **Search by name** field. You will also have to select a resource account associated to the auto attendant. The caller who selects this option is sent to that auto attendant.
- **Call queue** Select the name of an existing call queue in the **Search by name** field. You will also have to select a resource account associated to the call queue. The caller who selects this option is sent to that call queue, where the call is answered by a call agent.
- **External phone number** routes the caller to a designated phone number outside your local system.<!-- does this have prerequisites like direct routing?
- **Group Voicemail** routes the call to a voicemail box that you select.  -->

![Ícone do número 6, um balão na pesquisa anterior de ](media/teamscallout6.png) **diretório** de captura de tela nesta seção, você pode habilitar a **discagem por nome** e **discar por extensão** para o atendedor automático.   Você pode definir quem é e não está incluído nesses serviços na página de escopo opcional de discagem. Pesquisa de diretório é definida como **None** por padrão.

**Discar por nome** Se você habilitar essa opção, os chamadores poderão procurar pessoas em sua organização usando **discar por nome**. Eles dizem que o nome do usuário e o reconhecimento de voz correspondem a um usuário. Você pode definir quem é e não está incluído nesses serviços na página de escopo opcional de discagem. Qualquer usuário online com uma licença de sistema telefônico ou qualquer usuário hospedado no local usando o Skype for Business Server é um usuário elegível e pode ser encontrado com o nome discado.


**Discar por extensão** Se você habilitar essa opção, os chamadores poderão se conectar com os usuários em sua organização inserindo a extensão de seu telefone. Você pode selecionar quais usuários estão listados como disponíveis ou não estão disponíveis para **discar por extensão** na página de escopo opcional de discagem. Qualquer usuário online com uma licença do sistema telefônico ou qualquer usuário hospedado no local usando o Skype for Business Server é um usuário elegível e pode ser encontrado com a extensão dial-to.

> [!IMPORTANT]
> Por favor, observe o seguinte:
>- Os usuários que você deseja disponibilizar pela extensão de discagem precisam ter uma extensão especificada como parte de um dos seguintes atributos de telefone definidos no Active Directory ou Active Directory do Azure (consulte [adicionar usuários individualmente ou em massa] para obter mais informações ( https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) .
>    - HomePhone
>    - Celular/MobilePhone
>    - TelephoneNumber/intervalo
>    - OtherTelephone
>- O formato obrigatório para inserir a extensão no campo de número de telefone do usuário é `+<phonenumber>;ext=<extension>` ou `x<extension>` .
>- Não há suporte para a atribuição de uma extensão no centro de administração do teams no momento. Você deve usar o comando [set-MsolUser](https://docs.microsoft.com/powershell/module/msonline/set-msoluser?view=azureadps-1.0) do PowerShell ou o centro de administração do Microsoft 365.
>- Pode levar até 12 horas antes que as alterações nos atributos AAD intervalo e MobilePhone estejam disponíveis.
>- Não defina uma extensão para o LineUri de um usuário. Não há suporte para isso no momento.
>- Um atendedor automático pode ser configurado para discar por nome ou discar por extensão, mas não ambos.

> [!NOTE]
> Se quiser usar os recursos **discar por nome** e **discar pelos** recursos de extensão, você pode criar o atendedor automático principal (habilitado para **discar por nome**) que solicita que os chamadores escolham uma opção de menu se saberem a extensão do usuário e definir essa opção para transferir a chamada para um atendedor automático habilitado para discar por extensão.

* * *

<!--
**Instructions for callers** lets you choose **Use recorded call instructions** or **Write your call instructions**.  

If you choose **Use recorded call instructions**, you have the option to record and upload new or prerecorded sound files to play as menu instructions. The same app used in recording the auto attendant greeting is used here.

If you choose **Write your call instructions**, enter the script  you want the system to read (up to 1000 characters). For example, you might enter text that begins "Please choose from one of the following menu options ... " and provide a script written to reflect your configuration.
* * *  -->

Quando terminar de fazer suas seleções, clique em **Avançar** se desejar alterar as configurações avançadas ou clique em **Enviar** se quiser usar as configurações padrão para itens como:
- Fluxo de chamadas por horas extras
- Fluxo de chamadas para feriados
- Escopo de discagem
- Contas de recursos

Como o atendedor automático é necessário para ter uma conta de recurso, você tem a opção de prosseguir para a página da **conta do recurso** e associar uma conta de recurso que você já configurou ou criar uma conta de recurso e associá-la ao atendedor automático, conforme descrito em [gerenciar contas de recursos no Microsoft Teams](manage-resource-accounts.md). Você não poderá usar esse atendedor automático até que ele tenha sido associado a uma conta do recurso. para fazer isso, clique no botão **Avançar** na parte inferior da tela e, em seguida, clique em **contas de recurso** no painel de navegação à esquerda para ir diretamente para a página contas do recurso e associar o atendedor automático a uma conta de recurso.

#### <a name="advanced-settings-optional"></a>Configurações avançadas (opcional)

Há quatro telas adicionais que você pode configurar ou deixar com os padrões conforme escolher.

##### <a name="call-flow-for-after-hours"></a>Fluxo de chamadas por horas extras

Por padrão, o horário comercial do atendente automático é definido como 9h às 17h, de segunda a sexta-feira  <!--24/7-->e as opções de fluxo de chamadas para as chamadas de *horas* extras são desabilitadas porque todas as horas são consideradas no *horário comercial*. Quando você seleciona a opção **Configurar o horário comercial personalizado** , a página **fluxo de chamadas para horas** extras configura as regras de manipulação de chamadas usadas pelo atendedor automático após horas. As opções disponíveis são iguais, a diferença é a capacidade de definir um cronograma para diferentes menus e comportamentos.

Um sistema de atendedores automáticos só precisará definir o comportamento de manipulação de chamadas de horas para o atendedor automático de primeiro nível. Atendedores automáticos aninhados podem não ser chamados pelo atendedor automático de primeiro nível, mas, como alternativa, o sistema pode definir o comportamento de horas extras para cada atendedor automático usado.

Inicialmente, o horário comercial é definido para começar em 12:00 e terminar às 12:00 PM, de domingo a sábado. Todas as horas que não estão durante o horário comercial são consideradas *após o expediente*.


![captura de tela das configurações do fluxo de chamadas de horas extras](media/aa-afterhour.png)
 * * *

![Ícone do número 1, um texto explicativo na captura de tela anterior, ](media/teamscallout1.png) você pode clicar em **selecionar 24/7** para fazer todas as horas de trabalho para este atendedor automático.

![Ícone do número 2, um texto explicativo na captura de tela anterior, ](media/teamscallout2.png) Selecione a opção **Redefinir para padrão** para reverter todas as alterações no cronograma e retorne à definição padrão de horas comerciais como 9:00 am a 5:00 PM de segunda a sexta-feira.

![Ícone do número 3, um texto explicativo na captura de tela anterior, ](media/teamscallout3.png) selecione **limpar todas as horas** para limpar completamente o cronograma. A seleção dessa opção e a saída de horas não é recomendável, portanto Use essa opção somente se desejar refazer o horário comercial.

![Ícone 4, um texto explicativo no ícone de captura de tela anterior ](media/teamscallout4.png) ![ do número 5, um texto explicativo na captura de tela anterior ](media/teamscallout5.png) para personalizar a hora de início ou de término para um dia da semana, clique em **Iniciar em** ou **terminar no** momento em que deseja redefinir e selecione o novo horário na lista exibida.   A lista permite que você selecione o horário comercial em intervalos de 15 minutos, e o horário comercial selecionado aqui é baseado no fuso horário que você definiu na página **informações gerais** .

 <!-- The **Apply to all days** option can be used to reset all days of the week to match the settings for that day. This makes setting weekdays and weekends to different hours easier.-->

![Ícone do número 6, um texto explicativo na captura de tela anterior ](media/teamscallout6.png) para configurar uma pausa (um almoço, por exemplo), selecione **Adicionar novo horário** para esse dia da semana para criar uma nova linha de tabela e selecionar novos horários de início e de término. Você pode definir várias quebras dentro do horário comercial.

As opções de [fluxo de chamadas](#call-flow) disponíveis após horas são iguais às opções disponíveis durante o horário comercial. Role a tela para baixo na página de entrada de informações para definir as opções de fluxo de chamadas após horas.

* * *

Quando terminar de selecionar as opções, clique em **Avançar**. Você também pode clicar em **contas de recurso** no painel de navegação à esquerda para ir diretamente para a página contas do recurso e associar o atendedor automático a uma conta do recurso.

##### <a name="call-flow-during-holidays"></a>Fluxo de chamadas durante feriados

<a name="holidaygreetings"> </a>

Você pode adicionar até 20 feriados agendados para cada atendedor automático. Sua organização pode já ter definido feriados, conforme descrito em [Configurar feriados no Microsoft Teams](set-up-holidays-in-teams.md). Se não for exibida a seguinte tela: 

![Captura de tela: não há feriados configurados](media/aa-no-holidays.png)

![Ícone do número 1, um texto explicativo na captura de tela anterior ](media/teamscallout1.png) para definir um fluxo de chamadas personalizado para um feriado no atendedor automático, clique em **+ Adicionar** a tela ver o **novo fluxo de chamadas de feriados** .
> [!TIP]
> Para criar feriados, você pode ir para a tela em feriados de **configurações de toda a organização**  >  **Holidays**.  



![Captura de tela: adicionar um manipulador de chamadas](media/50a5ce88-7f39-4210-808a-da7ced969854b.png)

* * *

![Ícone do número 1, um texto explicativo na captura de tela anterior ](media/teamscallout1.png) Insira um **nome** para seu novo fluxo de chamadas.

![Ícone do número 2, um texto explicativo na captura de tela anterior ](media/teamscallout2.png) se você já tiver criado feriados, verá-os no menu suspenso **feriados** e poderá selecioná-los. Você pode ver uma opção não utilizada que pode ser editada para o que você precisa. Caso contrário, clique em **Adicionar** na parte inferior da lista suspensa para criar um novo feriado.  Consulte [Configurar feriados no Microsoft Teams](set-up-holidays-in-teams.md) para obter as etapas usadas para criar um feriado. 

Um nome de fluxo de chamadas de feriados pode ter até 64 caracteres de comprimento e deve ser exclusivo para a organização. Por exemplo, você não pode ter dois fluxos de chamadas de Natal chamados "de Graças" na mesma organização. O atendedor automático pode ter um fluxo de chamadas para cada feriado que você configurou, mas talvez queira ter um conjunto comum de comportamentos planejados que não sejam uma saudação personalizada.

![O ícone do número 3, um balão na captura de tela anterior, ](media/teamscallout3.png) as opções de [saudação](#call-flow) disponíveis para um fluxo de chamadas de feriados são iguais às opções disponíveis durante o horário comercial. As **ações** executadas após a saudação também são semelhantes, exceto que as únicas ações disponíveis são para **Desconectar** ou **redirecionar**e, ao escolher a opção **redirecionar para** , o operador não é uma das opções disponíveis. Você não pode configurar um menu específico para um fluxo de feriados.

> [!NOTE]
> Por padrão, todas as chamadas recebidas durante um período de feriado são definidas como **Desconectar** após a saudação (se houver), portanto, você deve especificar um redirecionamento se desejar um comportamento personalizado.

![Captura de tela da página fluxos de chamadas durante feriados](media/50a5ce88-7f39-4210-808a-da7ced969854.png)

Clique em salvar para concluir a criação do fluxo de chamadas de feriados. Depois que você criar um fluxo de chamadas de feriados, ele será exibido na tela **fluxos de chamadas durante feriados** .

Clique em **ao lado** de definir escopo de discagem, de **volta** para fazer alterações em fluxos de chamadas por hora e **Enviar** se você tiver terminado. Você também pode clicar em **contas de recurso** no painel de navegação à esquerda para ir diretamente para a página contas do recurso e associar o atendedor automático a uma conta do recurso.

#### <a name="dial-scope"></a>Escopo de discagem

<a name="dialscope"> </a>

![Captura de tela mostrando a página de escopo de discagem](media/1bcb185c-00db-43a7-b5c4-9b021c0627f7.png)

Nesta página, você pode definir quem está listado no seu diretório e disponível para discar por nome quando uma pessoa chama a sua organização. Discar por nome é definido como **desativado** por padrão em uma tela anterior. Todos os usuários com uma extensão estarão disponíveis se a **discagem por extensão** tiver sido selecionada anteriormente.

![Ícone do número 1, um texto explicativo na captura de tela anterior ](media/teamscallout1.png) **inclui** as opções desta seção são **todos os usuários online** ou **grupos de usuários personalizados**

Se você selecionar **todos os usuários online**, todos os usuários qualificados serão incluídos na pesquisa de diretório.

**Grupos de usuários personalizados** Essa opção permite pesquisar e selecionar um grupo, uma lista de distribuição ou um grupo de segurança do Microsoft 365 já criado em sua organização. Os usuários são adicionados ao diretório se estiverem no grupo do Microsoft 365, lista de distribuição ou grupo de segurança escolhido, e eles forem **usuários online com uma licença do sistema de telefone** ou hospedados no local usando o Skype for Business Server. Você pode adicionar vários grupos do Microsoft 365, listas de distribuição e grupos de segurança ao diretório.

<a name="dialscope"> </a>

Nesta página, você pode configurar quais usuários em sua organização serão listados em seu diretório e disponíveis para discar por nome quando uma pessoa ligar para a sua organização.

![Ícone do número 2, um texto explicativo na captura de tela anterior ](media/teamscallout2.png) **exclui** as opções desta seção permite excluir usuários ou grupos de usuários específicos do diretório da organização.

Se você selecionar **nenhum**, todos os usuários qualificados serão incluídos na pesquisa de diretório.

**Grupo de usuários personalizado** Você pode procurar um grupo, uma lista de distribuição ou um grupo de segurança do Microsoft 365 que tenha sido criado em sua organização. Os usuários desse grupo são excluídos da pesquisa de diretório. Você pode adicionar vários grupos do Microsoft 365, listas de distribuição e grupos de segurança.

Se você deixar as configurações no padrão quando discar por nome estiver habilitada, todos os usuários qualificados serão incluídos na pesquisa de diretório.

> [!NOTE]
> Pode levar até 36 horas para que um novo usuário tenha o nome listado no diretório. Quando alguém usa o recurso discar por nome com reconhecimento de fala, novas contas podem não estar disponíveis para esse recurso.

Depois de inserir todos os campos obrigatórios e configurar os menus e as opções de manipulação de chamadas, clique em **Avançar** para continuar a associar uma conta de recurso.

#### <a name="resource-accounts"></a>Contas de recursos

Todos os atendedores automáticos devem ter uma conta de recurso associada.  Os atendedores automáticos de primeiro nível precisarão, pelo menos, uma conta de recurso que tenha um número de serviço associado. Se quiser, você pode atribuir várias contas de recurso a um atendedor automático, cada uma com um número de serviço separado.

Se você ainda não configurou uma conta de recurso para o atendedor automático, você veria a seguinte tela: 

![captura de tela: gerenciamento de contas de recursos opcionais](media/aa-ra-optional.png) 

![Ícone do número 1, um texto explicativo na captura de tela anterior ](media/teamscallout1.png) para adicionar uma ou mais contas de recursos existentes e não atribuídos ao atendedor automático, clique em **Adicionar contas** e em Pesquisar e selecione-os nas caixas de diálogo fornecidas.

![captura de tela do novo assistente de resumo do atendente](media/aa-assigned.png)

![Ícone do número 1, um texto explicativo na captura de tela anterior ](media/teamscallout1.png) para adicionar uma conta de recurso adicional, clique em **+ adicionar conta**.

![Ícone do número 2, um texto explicativo na captura de tela anterior](media/teamscallout2.png) A conta do recurso ou contas atribuídas a este atendedor automático são mostradas em uma lista.

## <a name="edit-auto-attendants"></a>Editar atendedores automáticos

Depois de salvar seu novo atendedor automático, ele estará listado na página **atendedores automáticos** . Essa página permite que você veja rapidamente algumas das opções que você configurou, incluindo o nome, a conta de recurso associado, o idioma e o operador atribuído.

![captura de tela da lista de atendedores](media/aa-list.png)

Se você quiser alterar as configurações do atendedor automático, selecione o atendedor automático e, no painel Ação, clique em **Editar**.

<!-- To quickly place a test call to your auto attendant, click the **Test** button in the Action pane. -->

<!-- ## Summary view

You can use the Summary page to review the settings you've created.

![screenshot of the new attendant summary view](media/aa-new-summary.png)

Press the **Create** button to finish setup of your new auto attendant. -->

### <a name="create-an-auto-attendant-with-powershell"></a>Criar um atendedor automático com o PowerShell

Você também pode usar o PowerShell para criar e configurar atendedores automáticos. Estes são os cmdlets necessários para gerenciar um atendedor automático:

- [New-CsAutoAttendant](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant?view=skype-ps)  
- [Set-CsAutoAttendant](https://docs.microsoft.com/powershell/module/skype/set-csautoattendant?view=skype-ps)
- [Get-CsAutoAttendant](https://docs.microsoft.com/powershell/module/skype/get-csautoattendant?view=skype-ps)
- [Get-CsAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/get-csautoattendantholidays?view=skype-ps)
- [Remove-CsAutoAttendant](https://docs.microsoft.com/powershell/module/skype/remove-csautoattendant?view=skype-ps)
- [New-CsAutoAttendantMenu](https://docs.microsoft.com/powershell/module/skype/new-csautoattendantmenu?view=skype-ps)
- [New-CsOnlineAudioFile](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineAudioFile?view=skype-ps)
- [New-CsAutoAttendantCallFlow](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallFlow?view=skype-ps)
- [Export-CsAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/export-csorganizationalautoattendantholidays?view=skype-ps)
- [New-CsOnlineTimeRange](https://docs.microsoft.com/powershell/module/skype/new-csonlinetimerange?view=skype-ps)
- [New-CsOnlineDateTimeRange](https://docs.microsoft.com/powershell/module/skype/new-csonlinedatetimerange?view=skype-ps)
- [New-CsOnlineSchedule](https://docs.microsoft.com/powershell/module/skype/New-CsOnlineSchedule?view=skype-ps)
- [Get-CsAutoAttendantSupportedTimeZone](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone?view=skype-ps)
- [New-CsAutoAttendantCallHandlingAssociation](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation?view=skype-ps)
- [Get-CsAutoAttendantSupportedLanguage](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage?view=skype-ps)
- [Import-CsAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/import-csautoattendantholidays?view=skype-ps)
- [New-CsAutoAttendantCallableEntity](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallableEntity?view=skype-ps)

### <a name="more-about-windows-powershell"></a>Mais sobre o Windows PowerShell

- O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Microsoft 365 ou o Office 365 e o Microsoft Teams a partir de um único ponto de administração que pode simplificar o seu trabalho diário. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:

  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [Por que você precisa usar o PowerShell do Office 365](https://docs.microsoft.com/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade apenas usando o centro de administração do Microsoft 365, como as alterações de configuração de vários usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos:

  - [Gerenciar o Microsoft 365 ou o Office 365 com o Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [Usar o Windows PowerShell para gerenciar o Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a>Tópicos relacionados

[Veja o que você obtém com o Sistema de Telefonia](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[Obter números de telefone de serviço](/microsoftteams/getting-service-phone-numbers)

[Disponibilidade de Audioconferência e Planos de Chamadas por país e região](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

[New-CsOrganizationalAutoAttendant](https://docs.microsoft.com/powershell/module/skype/new-csorganizationalautoattendant?view=skype-ps)  

[Quais são os atendedores automáticos do Cloud?](what-are-phone-system-auto-attendants.md)

[Exemplo de pequena empresa – configurar um atendedor automático](/microsoftteams/tutorial-org-aa)  
