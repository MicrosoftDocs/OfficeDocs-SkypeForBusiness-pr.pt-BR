---
title: Configurar um assistente automático para o Microsoft Teams - tutorial de pequenas empresas
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: dobro
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
description: Saiba como configurar e testar os atendimentos automáticos para o Microsoft 365 Business Voice.
ms.openlocfilehash: 7fb9a9509354f5f6e3a17b2323eeaf2b5872e96e
ms.sourcegitcommit: 71d90f0a0056f7604109f64e9722c80cf0eda47d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/09/2021
ms.locfileid: "51656737"
---
# <a name="set-up-an-auto-attendant---small-business-tutorial"></a>Configurar um atendimento automático - tutorial de pequenas empresas

Os atendentes automáticos permitem que as pessoas liguem para sua organização e naveguem por um sistema de menus para falar com o departamento certo, fila de chamada, pessoa ou operador. Você pode criar assistentes automáticos para sua organização com o centro de administração do Microsoft Teams.

#### <a name="before-you-begin"></a>Antes de você começar

Obter os números de serviço necessários para os atendimentos automáticos que você deseja que sejam acessíveis discando diretamente de fora da sua organização. Isso pode incluir [a transferência de números de outro provedor ou](../phone-number-calling-plans/transfer-phone-numbers-to-teams.md) a [solicitação de novos números de serviço.](../getting-service-phone-numbers.md)

Obter um [Sistema de Telefonia - Licença de](../teams-add-on-licensing/virtual-user.md) usuário virtual para cada atendimento automático que você planeja criar. Essas licenças são gratuitas, portanto, sugerimos obter alguns extras caso você decida fazer alterações em sua instalação no futuro.

Se você quiser que sua rota de atendimento automático seja chamada de forma diferente nos [feriados,](../set-up-holidays-in-teams.md) crie os feriados que deseja usar antes de criar o atendimento automático.

<a name="steps"></a>

#### <a name="follow-these-steps-to-set-up-your-auto-attendant"></a>Siga estas etapas para configurar o seu assistente automático

# <a name="step-1brphone-number"></a>[Etapa 1 <br> Número de telefone](#tab/phone-number)

Cada atendimento automático criado requer uma conta de recurso. Isso é semelhante a uma conta de usuário, exceto que a conta está associada a um atendimento automático ou fila de chamada em vez de uma pessoa. Nesta etapa, criaremos a conta, atribuiremos a ela um Sistema de Telefonia do *Microsoft 365 -* Licença de usuário virtual e atribuiremos um número de serviço.

### <a name="create-a-resource-account"></a>Criar uma conta de recurso

Você pode criar uma conta de recurso no centro de administração do Teams.

1. No centro de administração do Teams, expanda **configurações** em toda a organização e clique em **Contas de recursos.**

2. Clique em **Adicionar**.

3. No painel **Adicionar conta de** recurso, preencha **Nome** de exibição , Nome de **usuário** e escolha **Atendimento** automático para o tipo de conta **de recurso**

    ![Captura de tela da interface do usuário adicionar conta de recurso](../media/resource-account-add.png)

4. Clique em **Salvar**.

    A nova conta aparecerá na lista de contas.

    ![Captura de tela de uma lista de contas de recursos](../media/resource-accounts-page.png)

### <a name="assign-a-license"></a>Atribuir uma licença

Você deve atribuir uma licença do Sistema de Telefonia do *Microsoft 365 - Usuário Virtual* à conta de recurso.

1. No Centro de administração do Microsoft 365, clique na conta de recurso à qual você deseja atribuir uma licença.

2. Na guia **Licenças e Aplicativos,** em **Licenças,** selecione Sistema de Telefonia do **Microsoft 365 - Usuário Virtual**.

3. Clique **em Salvar alterações**.

    ![Captura de tela da interface do usuário atribuir licenças no centro de administração do Microsoft 365](../media/resource-account-assign-virtual-user-license.png)

### <a name="assign-a-service-number"></a>Atribuir um número de serviço

Se você precisar que esse atendimento automático seja acessível por um número de telefone, atribua esse número à conta de recurso.

1. No Centro de administração  do Teams, na página Contas de recursos, selecione a conta de recurso à qual você deseja atribuir um número de serviço e clique em **Atribuir/desatribuição.**

2. No menu **suspenso Tipo de** número de telefone, escolha o tipo de número que você deseja usar.

3. Na caixa **Número de telefone atribuído,** pesquise o número que deseja usar e clique em **Adicionar**.

    ![Captura de tela da interface do usuário atribuir número de serviço](../media/resource-account-assign-phone-number.png)

4. Clique em **Salvar**.

> [!div class="nextstepaction"]
> [Etapa 2 - Informações gerais do atendimento automático >](/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?tabs=general-info#steps)

# <a name="step-2brattendant-general-info"></a>[Etapa 2 <br> Informações gerais do atendente](#tab/general-info)

Para configurar um atendimento automático

1. No centro de administração do Teams, **expanda Voz,** clique em **Atendimento automático** e clique em **Adicionar**.

2. Digite um nome para o atendimento automático na caixa na parte superior.

3. Se você quiser designar um operador, especifique o destino das chamadas para o operador. Isso é opcional (mas recomendado). Você pode definir a **opção Operador** para permitir que os chamadores possam sair dos menus e falar com uma pessoa designada.

4. Especifique o fuso horário desse atendimento automático. O fuso horário é usado para calcular o horário comercial se você criar um fluxo de chamada separado para depois do horário.

5. Especifique um idioma para esse atendimento automático. Esse é o idioma que será usado para prompts de voz gerados pelo sistema.

6. Escolha se deseja habilitar entradas de voz. Quando habilitada, o nome de cada opção de menu se torna uma palavra-chave de reconhecimento de fala. Por exemplo, os chamadores podem dizer "Um" para selecionar a opção de menu mapeada para a tecla 1 ou podem dizer "Vendas" para selecionar a opção de menu chamada "Vendas".

    ![Captura de tela das configurações de atendimento automático para nome, operador, fuso horário, idioma e entradas de voz](../media/auto-attendant-general-info-page-new.png)

7. Click **Next**.

> [!div class="nextstepaction"]
> [Etapa 3 - Fluxo de chamada >](/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?tabs=call-flow#steps)

# <a name="step-3brcall-flow"></a>[Etapa 3 <br> Fluxo de chamada](#tab/call-flow)

Escolha suas opções de fluxo de chamada

1. Escolha se deseja reproduzir uma saudação quando o atendente automático atender uma chamada.

    Se você selecionar **Reproduzir um arquivo de áudio,** poderá usar o botão **Carregar** arquivo para carregar uma mensagem de saudação gravada salva como áudio em . WAV, . MP3 ou . Formato WMA. A gravação não pode ser maior do que 5 MB.

    Se você selecionar **Digitar uma** mensagem de saudação, o sistema lerá o texto que você digitará (até 1000 caracteres) quando o atendemento automático atender a uma chamada.

    ![Captura de tela das configurações da mensagem de saudação](../media/auto-attendant-call-flow-greeting-message.png)

2. Escolha como você deseja rotear a chamada.

    Se você selecionar **Desconectar,** o atendimento automático desligará a chamada.

    Se você selecionar **Redirecionar chamada,** poderá escolher um dos destinos de roteamento de chamadas.

    Se você selecionar Opções de menu  Reproduzir, poderá  optar por Reproduzir um arquivo de áudio ou Digitar uma mensagem de saudação e escolher entre opções de **menu** e pesquisa de diretório.

    ![Captura de tela das configurações de roteamento de chamadas](../media/auto-attendant-call-flow-route-call-message.png)

3. Se você quiser que os chamadores usem teclas de discagem para navegar, em Definir opções de **menu,** escolha o que você deseja que aconteça quando os chamadores pressionarem uma tecla de discagem. (Se você estiver criando esse atendimento automático como um diretório da empresa, deixe as opções da chave de discagem em branco.)

    Você pode definir qualquer uma das teclas de discagem para os seguintes destinos:

    - **Pessoa na organização** - uma pessoa em sua organização que é capaz de receber chamadas de voz.
    - **Aplicativo de voz** - outro atendimento automático ou uma fila de chamadas.
    - **Número de telefone externo** - qualquer número de telefone. Use este formato: +[código do país][código de área][número de telefone]
    - **Caixa** postal - a caixa de correio de voz associada a um grupo do Microsoft 365 especificado.
    - **Operador** - o operador definido para o atendimento automático. Definir um operador é opcional. O operador pode ser definido como qualquer um dos outros destinos nesta lista.

    Recomendamos a configuração de 0 tecla para o operador.

    Para cada opção de menu, especifique o seguinte:

    - **Tecla de** discagem - a chave no teclado do telefone para acessar essa opção.

    - **Comando de** voz - define o comando de voz que um chamador pode dar para acessar essa opção, se as entradas de voz estão habilitadas. Ele pode conter várias palavras como "Atendimento ao Cliente" ou "Operações e Motivos". 

    - **Redirecionar** para onde você deseja que a chamada vá quando os chamadores escolherem essa opção. Se você estiver redirecionando para um atendimento automático ou fila de chamada, escolha a conta de recurso associada a ela.

    ![Captura de tela das opções de teclas de discagem](../media/auto-attendant-call-flow-menu-options-complete.png)

4. Se você quiser usar esse assistente automático como diretório da empresa, em **Pesquisa de** diretório, selecione **Discar por nome**. Quando você habilita essa opção, os chamadores podem dizer o nome do usuário ou digitá-lo no teclado do telefone. Qualquer usuário online com uma licença do Sistema de Telefonia é um usuário qualificado e pode ser encontrado com Dial pelo nome. 

    (Você pode escolher **Discar por extensão**, no entanto, a extensão deve ser configurada no Azure Active Directory.)

5. Depois de selecionar uma opção **de pesquisa de diretório,** clique em **Próximo**.

> [!div class="nextstepaction"]
> [Etapa 4 - Fluxo de chamada após o horário >](/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?tabs=after-hours#steps)

# <a name="step-4brafter-hours"></a>[Etapa 4 <br> Após horas](#tab/after-hours)

O horário comercial pode ser definido para cada atendimento automático. Se os horários comerciais não forem definidos, todos os dias e todas as horas do dia serão considerados horários comerciais, porque um cronograma 24/7 é definido por padrão. O horário comercial pode ser definido com pausas no tempo durante o dia e todas as horas que não estão definidas como horário comercial são consideradas após o horário. Você pode definir diferentes opções de tratamento de chamadas de entrada e saudações para o pós-horário.

Dependendo de como você configurou seus atendimentos automáticos e filas de chamadas, talvez seja necessário especificar apenas o roteamento de chamadas após o horário para os atendimentos automáticos com números de telefone diretos.

Se você quiser roteamento de chamadas separado para chamadores após o horário, especifique seu horário comercial para cada dia. Clique **em Adicionar novo horário** para especificar vários conjuntos de horas para um determinado dia, por exemplo, para especificar uma pausa de almoço.

![Captura de tela das configurações de dia e hora após o expediente](../media/auto-attendant-business-hours.png)

Depois de especificar seu horário comercial, escolha suas opções de roteamento de chamadas para o horário de expediente. As mesmas opções estão disponíveis para o roteamento de chamadas de horário comercial especificado na **Etapa 3 - Fluxo de chamadas.**

Clique **em Próximo** quando terminar.

> [!div class="nextstepaction"]
> [Etapa 5 - Fluxo de chamada de feriado >](/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?tabs=holidays#steps)

# <a name="step-5brholidays"></a>[Etapa 5 <br> Feriados](#tab/holidays)

Você pode ter chamadas para o seu atendimento automático roteados de forma diferente em feriados do que em outros dias. (Se você não quiser ter um fluxo de chamada diferente para feriados, ignore esta etapa.)



O seu atendente automático pode ter um fluxo de chamada para cada feriado que você definiu. Você pode adicionar até 20 feriados agendados para cada atendedor automático.

1. Na página Configurações de chamada de feriado, clique em **Adicionar**.

2. Digite um nome para essa configuração de feriado.

3. No menu **suspenso Feriado,** escolha o feriado que você deseja usar.

4. Escolha o tipo de saudação que você deseja usar.

    ![Captura de tela das configurações de saudação de feriados e feriados](../media/auto-attendant-holiday-greeting.png)

5. Escolha se deseja **desconectar ou** **redirecionar** a chamada.

6. Se você optou por redirecionar, escolha o destino de roteamento de chamadas para a chamada.

    ![Captura de tela das configurações de ação de chamada de feriado](../media/auto-attendant-holiday-actions.png)

7. Clique em **Salvar**.

    Repita o procedimento conforme necessário para cada feriado adicional.
    
    ![Captura de tela das configurações de feriados com feriados listados](../media/auto-attendant-holiday-call-settings.png)
    
    Quando você adicionou todos os feriados, clique em **Próximo**.

> [!div class="nextstepaction"]
> [Etapa 6 - Escolher quem está no diretório >](/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?tabs=dial-scope#steps)

# <a name="step-6brdirectory-members"></a>[Membros do Diretório etapa 6 <br>](#tab/dial-scope)

O *escopo de* discagem define quais usuários estão disponíveis no diretório quando um chamador usa discagem por nome ou discagem por extensão. O padrão de **Todos os usuários online** inclui todos os usuários em sua organização que são usuários online com uma licença do Sistema de Telefonia.

Você pode incluir ou excluir  usuários específicos selecionando Grupo de usuários personalizado em **Incluir** ou **Excluir** e escolher um ou mais grupos, listas de distribuição ou grupos de segurança do Microsoft 365. Por exemplo, talvez você queira excluir executivos em sua organização do diretório de discagem. (Se um usuário estiver em ambas as listas, ele será excluído do diretório.)

![Captura de tela do escopo de discagem incluem e excluem opções](../media/auto-attendant-dial-scope.png)

> [!NOTE]
> Pode levar até 36 horas para que um novo usuário tenha seu nome listado no diretório.

Quando terminar de definir o escopo de discagem, clique em **Próximo**.

> [!div class="nextstepaction"]
> [Etapa 7 - Atribuir uma conta de recurso >](/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?tabs=resource-accounts#steps)

# <a name="step-7brresource-accounts"></a>[Etapa 7 <br> Contas de recursos](#tab/resource-accounts)

Todos os atendentes automáticos devem ter uma conta de recurso associada.  Os atendentes automáticos de primeiro nível precisarão de pelo menos uma conta de recurso que tenha um número de serviço associado. Se desejar, você pode atribuir várias contas de recurso a um atendimento automático, cada uma com um número de serviço separado.

Para adicionar uma conta de recurso

1. Clique **em Adicionar** e pesquisar a conta que você deseja adicionar. Clique **em Adicionar** e, em seguida, clique em **Adicionar**.

    ![Captura de tela do painel adicionar contas de conta de recurso](../media/auto-attendant-add-resource-account.png)

2. Quando terminar de adicionar contas de serviço, clique em **Enviar**.

    ![Captura de tela da lista de contas de recursos mostrando a conta de recurso com o número de serviço atribuído](../media/auto-attendant-resource-account-assigned.png)

    Isso conclui a configuração do atendimento automático.

---


