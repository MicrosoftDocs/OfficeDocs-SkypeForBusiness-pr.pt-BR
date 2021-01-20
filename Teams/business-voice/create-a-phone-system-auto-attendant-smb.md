---
title: Configurar um atendedor automático para o Microsoft Teams-tutorial para empresas de pequeno porte
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
description: Saiba como configurar e testar atendedores automáticos do Microsoft 365 Business Voice.
ms.openlocfilehash: b3b291a91c96d75acdc8d4fe77f78790d2137914
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909599"
---
# <a name="set-up-an-auto-attendant---small-business-tutorial"></a>Configurar um atendedor automático-tutorial para empresas de pequeno porte

Os atendedores automáticos permitem que as pessoas liguem para sua organização e naveguem em um sistema de menus para falar com o departamento certo, a fila de chamadas, a pessoa ou um operador. Você pode criar atendedores automáticos para sua organização com o centro de administração do Microsoft Teams.

#### <a name="before-you-begin"></a>Antes de você começar

Obtenha os números de serviço de que você precisa para os atendedores automáticos que você deseja que sejam acessíveis pela discagem direta de fora da sua organização. Isso pode incluir a [transferência de números de outro provedor](../phone-number-calling-plans/transfer-phone-numbers-to-teams.md) ou a [solicitação de novos números de serviço](../getting-service-phone-numbers.md).

Obter um [sistema telefônico-licença de usuário virtual](../teams-add-on-licensing/virtual-user.md) para cada atendedor automático que você planeja criar. Essas licenças são gratuitas, portanto, sugerimos que você tenha alguns recursos adicionais para que você decida fazer alterações na sua configuração no futuro.

Se quiser que seu atendedor automático faça chamadas de forma diferente nos feriados, [crie os feriados que você deseja usar](../set-up-holidays-in-teams.md) antes de criar o atendedor automático.

<a name="steps"></a>

#### <a name="follow-these-steps-to-set-up-your-auto-attendant"></a>Siga estas etapas para configurar o atendedor automático

# <a name="step-1brphone-number"></a>[Número de telefone da etapa 1 <br>](#tab/phone-number)

Cada atendedor automático que você cria exige uma conta de recurso. Isso é semelhante a uma conta de usuário, exceto que a conta é associada a um atendedor automático ou fila de chamada em vez de uma pessoa. Nesta etapa, criaremos a conta, atribuímos a ela um *sistema telefônico Microsoft 365-licença de usuário virtual* e, em seguida, atribuímos um número de serviço.

### <a name="create-a-resource-account"></a>Criar uma conta de recurso

Você pode criar uma conta de recurso no centro de administração do Microsoft Teams.

1. No centro de administração do Teams, expanda **configurações de toda a organização** e clique em **contas de recursos**.

2. Clique em **Adicionar**.

3. No painel **adicionar conta do recurso** , preencha o **nome para exibição**, o **nome de usuário** e escolha **atendedor automático** para o **tipo de conta de recurso**

    ![Captura de tela da interface do usuário da conta adicionar recurso](../media/resource-account-add.png)

4. Clique em **Salvar**.

A nova conta será exibida na lista de contas.

![Captura de tela de uma lista de contas de recursos](../media/resource-accounts-page.png)

### <a name="assign-a-license"></a>Atribuir uma licença

Você deve atribuir um *sistema telefônico Microsoft 365-licença de usuário virtual* para a conta do recurso.

1. No centro de administração do Microsoft 365, clique na conta de recurso à qual você deseja atribuir uma licença.

2. Na guia **licenças e aplicativos** , em **licenças**, selecione **sistema telefônico Microsoft 365-usuário virtual**.

3. Clique em **salvar alterações**.

    ![Captura de tela da interface do usuário de atribuir licenças no centro de administração do Microsoft 365](../media/resource-account-assign-virtual-user-license.png)

### <a name="assign-a-service-number"></a>Atribuir um número de serviço

Se você precisar que este atendedor automático seja alcançável por um número de telefone, atribua esse número à conta do recurso.

1. No centro de administração do Teams, na página **contas do recurso** , selecione a conta do recurso à qual você deseja atribuir um número de serviço e clique em **atribuir/Cancelar atribuição**.

2. Na lista suspensa **tipo de número de telefone** , escolha o tipo de número que você deseja usar.

3. Na caixa **número de telefone atribuído** , procure o número que deseja usar e clique em **Adicionar**.

    ![Captura de tela da interface de usuário atribuir número de serviço](../media/resource-account-assign-phone-number.png)

4. Clique em **Salvar**.

> [!div class="nextstepaction"]
> [Etapa 2-informações gerais sobre o atendedor automático >](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?branch=mikeplum-smb-voice&tabs=general-info#steps)

# <a name="step-2brattendant-general-info"></a>[<br>Informações gerais do atendente da etapa 2](#tab/general-info)

Para configurar um atendedor automático

1. No centro de administração do Teams, expanda **voz**, clique em **atendedores automáticos** e, em seguida, clique em **Adicionar**.

2. Digite um nome para o atendedor automático na caixa na parte superior.

3. Se você quiser designar um operador, especifique o destino para as chamadas para o operador. Isso é opcional (mas recomendado). Você pode definir a opção de **operador** para permitir que os chamadores quebrem nos menus e falar com uma pessoa designada.

4. Especifique o fuso horário para este atendedor automático. O fuso horário é usado para calcular o horário comercial se você criar um fluxo de chamadas separado para o expediente.

5. Especifique um idioma para este atendedor automático. Esse é o idioma que será usado para solicitações de voz geradas pelo sistema.

6. Escolha se deseja habilitar as entradas de voz. Quando habilitado, o nome de cada opção de menu se torna uma palavra-chave de reconhecimento de fala. Por exemplo, os chamadores podem dizer "um" para selecionar a opção de menu mapeada para a tecla 1 ou podem dizer "vendas" para selecionar a opção de menu chamada "vendas".

    ![Captura de tela das configurações do atendedor automático para nome, operador, fuso horário, idioma e entradas de voz](../media/auto-attendant-general-info-page-new.png)

7. Click **Next**.

> [!div class="nextstepaction"]
> [Etapa 3-fluxo de chamadas >](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?branch=mikeplum-smb-voice&tabs=call-flow#steps)

# <a name="step-3brcall-flow"></a>[Fluxo de chamadas da etapa 3 <br>](#tab/call-flow)

Escolha as opções de fluxo de chamadas

1. Escolha se deseja reproduzir uma saudação quando o atendedor automático atender a uma chamada.

    Se você selecionar **executar um arquivo de áudio** , poderá usar o botão **carregar arquivo** para carregar uma mensagem de saudação gravada salva como áudio. WAV,. MP3 ou. Formato WMA. A gravação não pode ter mais de 5 MB.

    Se você selecionar **digitar uma mensagem de saudação** , o sistema lerá o texto que você digitar (até 1000 caracteres) quando o atendedor automático atender a uma chamada.

    ![Captura de tela das configurações da mensagem de saudação](../media/auto-attendant-call-flow-greeting-message.png)

2. Escolha como você deseja direcionar a chamada.

    Se você selecionar **Desconectar**, o atendedor automático irá desligar a chamada.

    Se você selecionar **redirecionar chamada**, poderá escolher um dos destinos de roteamento de chamadas.

    Se você selecionar **Opções do menu reproduzir**, poderá optar por **reproduzir um arquivo de áudio** ou **digitar uma mensagem de saudação** e escolher entre as opções do menu e a pesquisa de diretório.

    ![Captura de tela das configurações de roteamento de chamadas](../media/auto-attendant-call-flow-route-call-message.png)

3. Se você quiser que os chamadores usem as teclas de discagem para navegar e, em seguida, em **definir opções do menu**, escolha o que você deseja que aconteça quando os chamadores pressionarem uma tecla de discagem. (Se você estiver criando este atendedor automático como um diretório da empresa, deixe as opções da tecla de discagem em branco.)

    Você pode definir qualquer uma das teclas de discagem para os seguintes destinos:

    - **Pessoa na organização** -uma pessoa em sua organização que pode receber chamadas de voz.
    - **Aplicativo de voz** -outro atendedor automático ou uma fila de chamadas.
    - **Número de telefone externo** – qualquer número de telefone. Use este formato: + [código do país] [código de área] [número de telefone]
    - Correio **de voz-a** caixa de correio de voz associada a um grupo do Microsoft 365 que você especificar.
    - **Operator** – o operador definido para o atendedor automático. A definição de um operador é opcional. O operador pode ser definido como qualquer um dos outros destinos nesta lista.

    Recomendamos configurar a tecla 0 para o operador.

    Para cada opção de menu, especifique o seguinte:

    - **Tecla de discagem** -a tecla no teclado do telefone para acessar esta opção.

    - **Comando de voz** -define o comando de voz que um chamador pode conceder para acessar essa opção, se as entradas de voz estiverem habilitadas. Ele pode conter várias palavras como "atendimento ao cliente" ou "operações e aterramento". 

    - **Redirecione para** -onde você deseja que a chamada se chame quando os chamadores escolherem esta opção. Se você estiver redirecionando para um atendedor automático ou fila de chamadas, escolha a conta do recurso associada a ele.

    ![Captura de tela das opções da tecla de discagem](../media/auto-attendant-call-flow-menu-options-complete.png)

4. Se você quiser usar esse atendedor automático como um diretório da empresa e, em **pesquisa de diretório**, selecione **discar por nome**. Quando você habilita essa opção, os chamadores podem dizer o nome do usuário ou digitá-lo no teclado do telefone. Qualquer usuário online com uma licença de sistema telefônico é um usuário elegível e pode ser encontrado com a discagem por nome. 

    (Você pode escolher a **extensão dial por**, no entanto, a extensão deve ser configurada no Azure Active Directory.)

5. Depois de selecionar uma opção de **pesquisa de diretório** , clique em **Avançar**.

> [!div class="nextstepaction"]
> [Etapa 4-após horas de chamadas de fluxo de chamadas >](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?branch=mikeplum-smb-voice&tabs=after-hours#steps)

# <a name="step-4brafter-hours"></a>[Etapa 4 <br> após horas](#tab/after-hours)

O horário comercial pode ser definido para cada atendedor automático. Se os horários comerciais não forem definidos, todos os dias e todas as horas do dia serão considerados horários comerciais, porque um cronograma 24/7 é definido por padrão. O horário comercial pode ser definido com quebras de horário durante o dia, e todas as horas que não estão definidas como horário comercial são consideradas após o expediente. Você pode definir diferentes opções de atendimento de chamadas e saudações por horas extras.

Dependendo de como você configurou seus atendedores automáticos e filas de chamadas, talvez você só precise especificar o roteamento de chamadas após a hora para atendedores automáticos com números de telefone diretos.

Se você quiser um encaminhamento de chamadas separado para chamadores após a hora e, em seguida, especifique o horário comercial para cada dia. Clique em **Adicionar novo horário** para especificar vários conjuntos de horas para um determinado dia, por exemplo, para especificar um intervalo de almoço.

![Captura de tela das configurações de horas e dia da hora](../media/auto-attendant-business-hours.png)

Depois de especificar o horário comercial, escolha as opções de roteamento de chamadas para o expediente. As mesmas opções estão disponíveis para o encaminhamento de chamadas do horário comercial que você especificou na **etapa 3-fluxo de chamadas**.

Clique em **Avançar** quando terminar.

> [!div class="nextstepaction"]
> [Etapa 5->de fluxo de chamadas de feriados ](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?branch=mikeplum-smb-voice&tabs=holidays#steps)

# <a name="step-5brholidays"></a>[Etapa 5 <br> feriados](#tab/holidays)

Você pode fazer com que as chamadas para o atendedor automático sejam roteadas de forma diferente em feriados do que em outros dias. (Se você não quiser ter um fluxo de chamadas diferente para feriados, pode ignorar esta etapa.)



O atendedor automático pode ter um fluxo de chamadas para cada feriado que você configurou. Você pode adicionar até 20 feriados agendados para cada atendedor automático.

1. Na página de configurações de chamadas de Natal, clique em **Adicionar**.

2. Digite um nome para esta configuração de feriado.

3. Na lista suspensa **feriado** , escolha o feriado que você deseja usar.

4. Escolha o tipo de saudação que você deseja usar.

    ![Captura de tela das configurações de saudação de feriado e feriado](../media/auto-attendant-holiday-greeting.png)

5. Escolha se deseja **Desconectar** ou **redirecionar** a chamada.

6. Se você optou por redirecionar, escolha o destino de roteamento de chamadas para a chamada.

    ![Captura de tela das configurações de ação das chamadas de Natal](../media/auto-attendant-holiday-actions.png)

7. Clique em **Salvar**.

Repita o procedimento conforme necessário para cada feriado adicional.

![Captura de tela das configurações de feriado com feriados listados](../media/auto-attendant-holiday-call-settings.png)

Depois de adicionar todos os seus feriados, clique em **Avançar**.

> [!div class="nextstepaction"]
> [Etapa 6-escolher quem está no diretório >](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?branch=mikeplum-smb-voice&tabs=dial-scope#steps)

# <a name="step-6brdirectory-members"></a>[Etapa 6 <br> membros do diretório](#tab/dial-scope)

O *escopo de discagem* define quais usuários estão disponíveis no diretório quando um chamador usa discar por nome ou discagem por extensão. O padrão de **todos os usuários online** inclui todos os usuários de sua organização que são usuários online com uma licença de sistema telefônico.

Você pode incluir ou excluir usuários específicos selecionando **grupo de usuários personalizado** em **incluir** ou **excluir** e escolhendo um ou mais grupos do Microsoft 365, listas de distribuição ou grupos de segurança. Por exemplo, talvez você queira excluir executivos de sua organização do diretório de discagem. (Se um usuário estiver em ambas as listas, eles serão excluídos do diretório.)

![Captura de tela das opções incluir e excluir do escopo de discagem](../media/auto-attendant-dial-scope.png)

> [!NOTE]
> Pode levar até 36 horas para que um novo usuário tenha o nome listado no diretório.

Quando terminar de configurar o escopo de discagem, clique em **Avançar**.

> [!div class="nextstepaction"]
> [Etapa 7-atribuir uma conta de recurso >](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?branch=mikeplum-smb-voice&tabs=resource-accounts#steps)

# <a name="step-7brresource-accounts"></a>[Etapa 7 <br> contas de recursos](#tab/resource-accounts)

Todos os atendedores automáticos devem ter uma conta de recurso associada.  Os atendedores automáticos de primeiro nível precisarão pelo menos uma conta de recurso que tenha um número de serviço associado. Se quiser, você pode atribuir várias contas de recurso a um atendedor automático, cada uma com um número de serviço separado.

Para adicionar uma conta de recurso

1. Clique em **adicionar conta** e procure a conta que você deseja adicionar. Clique em **Adicionar** e, em seguida, clique em **Adicionar**.

    ![Captura de tela da conta do recurso Adicionar painel de contas](../media/auto-attendant-add-resource-account.png)

2. Quando terminar de adicionar contas de serviço, clique em **Enviar**.

    ![Captura de tela da lista conta de recurso mostrando a conta do recurso com número de serviço atribuído](../media/auto-attendant-resource-account-assigned.png)

Isso conclui a configuração do atendedor automático.

---


