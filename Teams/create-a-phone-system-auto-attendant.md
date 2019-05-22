---
title: Configurar um atendedor automático do Cloud
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: makolomi
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
description: Saiba como configurar e testar atendedores automáticos da nuvem para a manipulação de chamadas eficiente para a sua organização.
ms.openlocfilehash: d4889f7a33306c970b73651bcaafe9f3e2c8009b
ms.sourcegitcommit: 2f8b9c7c8d20f2605d09cae4bbaeb10667f2ddea
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/21/2019
ms.locfileid: "34330920"
---
# <a name="set-up-a-cloud-auto-attendant"></a>Configurar um atendedor automático do Cloud

Os atendedores automáticos permitem que as pessoas liguem para sua organização e naveguem em um sistema de menus para obter o departamento certo, a fila de chamadas, a pessoa ou a operadora. Você pode criar um atendedor automático para sua organização usando o centro de administração do Microsoft Teams. Para criar um novo atendedor automático, vá para **voz** no painel de navegação esquerdo e, em seguida, selecione **atendedores** > automáticos**Adicionar novo**.

Se você quiser saber mais sobre atendedores automáticos, consulte [o que são atendedores automáticos da nuvem?](/microsoftteams/what-are-phone-system-auto-attendants)

> [!NOTE]
> Este artigo se aplica ao Microsoft Teams e ao Skype for Business online.



## <a name="step-1---get-started"></a>Etapa 1-Introdução

- Um atendedor automático é necessário para ter uma conta de recurso associada. Consulte [gerenciar contas de recursos no Teams](manage-resource-accounts.md) para obter detalhes sobre contas de recursos.
- Se você planeja atribuir um número de roteamento direto, será necessário adquirir e atribuir as seguintes licenças às contas \(do recurso Office 365 Enterprise E1, E3 ou E5 com o complemento do sistema telefônico.\)
- Se estiver atribuindo um número de serviço da Microsoft, você precisará adquirir e atribuir as seguintes licenças à sua conta \(de recurso Office 365 Enterprise E1, E3 ou e5, com o complemento do sistema de telefonia e um plano\)de chamadas.

> [!NOTE] 
> A Microsoft está trabalhando em um modelo de licenciamento sem custo para aplicativos como atendedores automáticos da nuvem e filas de chamadas, por ora, você precisa usar o modelo de licenciamento do usuário.

> [!CAUTION]
> Para obter e usar números de telefone gratuitos, você precisa configurar Créditos de Comunicação. Para fazer isso, consulte [O que são Créditos de Comunicação?](what-are-communications-credits.md) e [Configurar Créditos de Comunicação para a sua organização](set-up-communications-credits-for-your-organization.md).

> [!TIP]
> Para redirecionar chamadas para um operador ou uma opção de menu que seja um usuário online com uma licença do **sistema de telefonia** , você precisará habilitá-las para o Enterprise Voice ou atribuir planos de chamada no Office 365. Consulte [atribuir licenças do Skype for Business](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) ou [atribuir licenças do Microsoft Teams](assign-teams-licenses.md). Você também pode usar o Windows PowerShell. Por exemplo, execute:`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

## <a name="step-2---create-a-new-auto-attendant"></a>Etapa 2 - Criar um novo atendedor automático

> [!IMPORTANT]
> Cada atendedor automático é necessário para ter uma [conta de recurso](manage-resource-accounts.md)associada. Você deve criar a conta do recurso primeiro, então você pode associá-la ao atendedor automático.

### <a name="using-the-microsoft-teams-admin-center"></a>Usar o centro de administração do Microsoft Teams

No **centro de administração do Microsoft Teams**, clique em atendedores automáticos de **voz** > **** e, em seguida, clique em **+ novo**:

#### <a name="general-info-page"></a>Página de informações gerais

![New auto attendant page 1.](media/edacec94-9384-4a87-be0a-5c49a151287e.png)

* * *

![Número 1](media/sfbcallout1.png)

**Nome** Digite um nome de exibição descritivo para o atendedor automático. O nome é obrigatório e pode conter até 64 caracteres, incluindo espaços. Ele será listado na coluna **Nome** da guia **Atendedores automáticos**.

* * *

![Número 2](media/sfbcallout2.png)

**Conta do recurso** Clique neste botão para selecionar uma ou mais contas de recursos para se conectar ao seu novo atendedor automático. Todos os atendedores automáticos devem ter uma conta de recurso associada. Uma conta de recurso pode ter um número de telefone associado à conta, mas pode não. Um atendedor automático de nível superior geralmente tem uma conta de recurso com um número de telefone atribuído, mas o atendedor automático aninhado (usado como um menu de nível 2 ao qual o atendedor automático de primeiro nível se conecta) pode não ter um número de telefone atribuído à sua conta de recurso.

* * *

![Número 3](media/sfbcallout3.png)

**Fuso horário** Você deve definir o fuso horário para o atendedor automático, mas ele não precisa corresponder ao fuso horário do endereço principal de sua organização. Cada atendedor automático pode ter um fuso horário diferente e os horários comerciais definidos para o atendedor automático serão definidos com base no fuso horário que você selecionar aqui.

* * *

![Número 4](media/sfbcallout4.png)

**Idioma** Selecione o idioma que você deseja usar para o atendedor automático entre os idiomas disponíveis listados. O idioma que você define aqui é o idioma que o atendedor automático usará para interagir com as pessoas que chamam nesse atendedor automático, e todos os prompts do sistema serão reproduzidos nesse idioma.

* * *

![Número 5](media/sfbcallout5.png)

**Operador** Isso é opcional e não precisa ser definido para o atendedor automático. No entanto, você pode definir a opção de **operador** para as pessoas que chamam para que possam sair dos menus para falar com uma pessoa para ajudá-los.

A tecla 0 é atribuída automaticamente ao Operador.

Se você configurar isso, também precisará dizer às pessoas que chamam se essa opção está disponível nas **Opções do menu Editar** na página de **manipulação de chamadas do horário comercial** . Se você definir um operador em seu atendedor automático, será necessário inserir o texto de aviso correspondente na caixa **** os chamadores ouvirá ou alterar seu arquivo de áudio para incluir essa opção. Por exemplo, "Para falar com o operador, pressione 0".

Você pode definir um dos seguintes como Operador:

- **Pessoa da sua empresa** com uma licença de **Sistema de Telefonia** habilitada para Enterprise Voice ou com Planos de Chamadas do Office 365 atribuídos.

     > [!Note]
     > A **Pessoa da sua empresa** pode ser um usuário Online ou um usuário hospedado no local usando o Skype for Business Server 2015 ou o Lync Server 2013.

- Uma **fila de chamadas** que você configurou.
- Você pode configurá-lo para que a pessoa que liga seja enviada para a caixa postal. Para fazer isso, selecione **pessoa em sua empresa** e defina as chamadas desta pessoa para serem encaminhadas diretamente para o correio de voz.

* * *

![Número 6](media/sfbcallout6.png)

**Habilitar entradas de voz** O reconhecimento de fala estará disponível se esta opção for selecionada. As pessoas que chamam podem usar entrada de voz no [idioma que você definiu](set-auto-attendant-languages-for-audio-conferencing-in-teams.md). Você pode desativar o reconhecimento de fala definindo-o como desativado, se quiser permitir que as pessoas usem o teclado de telefone.

* * *

Quando terminar de selecionar as opções, clique em **Avançar**.

#### <a name="business-hours-page"></a>Página de horário comercial

Por padrão, o horário comercial é definido como 9h às 17:00, de segunda a sexta-feira.  Todos os horários que não estão incluídos nos horários comerciais são considerados horários fora do expediente. Você pode clicar em **selecionar 24/7** para fazer todas as horas de trabalho. A menos que você selecione a opção **selecionar 24/7** , a página de **configurações de chamada de horas** extras será usada para configurar a manipulação de chamadas de após o horário comercial para o atendedor automático.

![New auto attendant Hours of operation.](media/61769547-cdb4-45c0-af5a-3d6e0731fbc6.png)

* * *

![Número 1](media/sfbcallout1.png)

Por padrão, o horário comercial é definido como de segunda a sexta-feira, 9:00 am-5:00 PM. Selecione a opção **limpar todas as horas** para desmarcar todas as horas no cronograma. Quando você selecionar **Redefinir para padrão**, o horário comercial será redefinido para segunda a sexta-feira, 9:00 am-5:00 PM.

* * *

![Número 2](media/sfbcallout2.png)

Para alterar os horários comerciais, destaque os horários comerciais que deseja definir usando o calendário. O calendário permite que você selecione horários comerciais em intervalos de 30 minutos, e o horário comercial selecionado aqui será definido com base no fuso horário que você definiu na página **informações gerais** . Para configurar um intervalo (horário de almoço, por exemplo), desmarque ou arraste para desmarcar o horário no calendário. Você pode definir várias quebras dentro do horário comercial.

* * *

Quando terminar de selecionar as opções, clique em **Avançar**.

#### <a name="business-hours-call-settings"></a>Configurações de chamada para horário comercial

> [!TIP]
> Se você usar um cronograma personalizado de horário de trabalho, também precisará configurar o recurso de chamada para após o horário comercial usando a página de **processamento de chamadas de horas** extras, que lhe dará as mesmas opções que **as configurações de chamada do horário comercial**.

Você pode configurar saudações, prompts e menus para os quais as pessoas que ligarem para o número de telefone do atendedor automático da sua organização estarão ouvindo durante o horário comercial.

![Atendimento de chamadas em horário comercial. ](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)
O tratamento de chamadas do horário comercial continua continuado ![.](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8b.png)

* * *

![Número 1](media/sfbcallout1.png)

**Saudação** Uma saudação na hora da empresa é opcional e pode ser definida como **sem saudação**. Nesse caso, o chamador não ouvirá nenhuma mensagem ou saudação antes que a chamada seja manipulada por uma das ações que você selecionar. Você também pode carregar um arquivo de áudio (em formatos .wav, .mp3 ou. wma) ou criar uma saudação personalizada usando conversão de texto em fala.

- **Sem saudação** Nenhuma saudação será reproduzida quando as pessoas ligarem para o número de telefone do atendedor automático.
- **Carregar um arquivo de áudio** Se você escolher isso, grave a saudação e, em seguida, carregue seu arquivo de áudio (nos formatos. wav,. mp3 ou. WMA).
- **Digite uma mensagem de saudação** Se você escolher essa opção, insira o texto que deseja que o sistema Leia (até 1000 caracteres). Por exemplo, você pode inserir "Bem-vindo à Contoso. A sua ligação é muito importante para nós." na caixa **Os chamadores ouvirão**.

* * *

![Número 2](media/sfbcallout2.png)

Você pode selecionar o que acontece com as chamadas que chegam durante o horário comercial. Você pode escolher entre as seguintes ações:

- **Desconectar** Se você selecioná-lo, a pessoa que está ligando será desconectada depois de ouvir uma saudação de horário comercial.
- **Redirecionar chamada** Isso pode ser usado para enviar a chamada automaticamente para:
  - **Pessoa na empresa** com uma licença de **sistema telefônico** habilitada para Enterprise Voice ou planos de chamada atribuídos no Office 365. Você pode configurá-lo para que o chamador possa ser enviado para a caixa postal. Para fazer isso, selecione **pessoa na empresa** e defina esta pessoa para que as chamadas sejam encaminhadas diretamente para o correio de voz.

    > [!Note]
    > A **pessoa na empresa** pode ser um usuário online ou um usuário hospedado no local usando o Skype for Business Server 2015 ou o Lync Server 2013.

   - Outro **atendedor automático**

   Você pode usar um atendedor automático existente para criar um segundo nível de opções de menu contendo um submenu. These are called nested auto attendants. Para enviar a chamada para um atendedor automático aninhado, selecione **pessoa na empresa** e atribua uma conta de recurso, uma que já tenha um atendedor automático associado ou que você associe a um atendedor automático quando terminar de criar este atendedor automático.

- **As opções do menu reproduzir** também podem ser usadas para permitir que você configure uma solicitação que você deseja que seja reproduzida.

* * *

![Número 3](media/sfbcallout3.png)

**Prompt do menu** Para criar o prompt do menu principal, você pode usar a conversão de texto em fala ou carregar um arquivo de áudio (.wav, .mp3 ou .wma). Você pode digitar o prompt na caixa **definir a navegação no menu para chamadores** ou gravar um arquivo de áudio e dizer, por exemplo: "para vendas, digamos ou pressionar ou dizer 1. Para Serviços, pressione ou fale 2. Para Suporte ao Cliente, pressione ou fale 3. Para falar com o operador, pressione ou fale 0. Para ouvir este menu novamente, pressione a tecla de asterisco ou fale repetir". **Digite uma mensagem de saudação** Se você escolheu isso, insira o texto que deseja que o sistema Leia (até 1000 caracteres). **Carregar um arquivo de áudio** Se você escolher isso, deverá gravar a saudação e depois carregar o arquivo de áudio (nos formatos .wav, .mp3 ou .wma).

* * *

![Número 4](media/sfbcallout4.png)

**Configuração de opções de menu** As opções de menu usando os botões de tecla no teclado numérico podem ser adicionadas ou removidas. Para adicionar uma opção de menu, pressione **+ atribuir uma tecla de discagem**. Uma linha de opções correspondente aparecerá abaixo. Para excluir uma opção de menu, basta clicar à esquerda da tecla correspondente no controle do teclado e clicar no ícone de exclusão acima. A linha de mapeamento de teclas será removida.

> [!TIP]
> Você terá que atualizar os prompts de menu para o texto ou regravar o áudio separadamente ao adicionar às opções de remoção porque ele não será feito automaticamente para o prompt de menu existente.  
>
>Qualquer opção de menu pode ser adicionada e removida em qualquer ordem, e os mapeamentos de chave não precisam ser contínuos. É possível, por exemplo, criar um menu com as teclas 0, 1 e 3 mapeadas para as opções, enquanto a tecla 2 não é usada.

> [!NOTE]
> As chaves \* (repetir) e \# (verso) são reservadas pelo sistema e não podem ser reatribuídas. Se o reconhecimento de fala estiver habilitado, pressionar * corresponderá com "repetir" e # corresponderá com os comandos de voz "verso".

Para configurar as opções de menu, depois de selecionar as teclas de discagem, será necessário:

- Digite o **comando de voz** da opção. Pode ter até 64 caracteres de comprimento e pode conter várias palavras como "atendimento ao cliente" ou "operações e aterramento". Se o reconhecimento de fala estiver habilitado, o nome será reconhecido automaticamente e a pessoa que está ligando poderá pressionar 3, diga "três" ou diga "atendimento ao cliente" para selecionar a opção mapeada para a tecla 3.
- Selecione o local em que a chamada será enviada se a tecla correspondente for pressionada ou a opção for selecionada usando o reconhecimento de fala. A chamada pode ser enviada para:

  - **Operador** de Se o operador já estiver configurado, ele será automaticamente mapeado para a chave 0, mas também pode ser excluído ou reatribuído a uma chave diferente. If operator isn't set to any key, then the voice command "Operator" will be disabled too.
  - Uma **Pessoa da sua empresa** com uma licença de **Sistema de Telefonia** habilitada para Enterprise Voice ou com um Plano de Chamadas do Office 365 atribuído. Você pode configurá-lo para que o chamador possa ser enviado para a caixa postal. Para fazer isso, selecione **pessoa em sua empresa** e defina esta pessoa para que as chamadas sejam encaminhadas diretamente para o correio de voz.

    > [!Note]
    > A **Pessoa da sua empresa** pode ser um usuário Online ou um usuário hospedado no local usando o Skype for Business Server 2015 ou o Lync Server 2013. 
    - Outro **atendedor automático**

       Você pode usar um atendedor automático existente para criar um segundo nível de opções de menu contendo um submenu. These are called nested auto attendants. Para enviar a chamada para um atendedor automático aninhado, selecione **pessoa na empresa** e atribua uma conta de recurso, uma que já tenha um atendedor automático associado ou que você associe a um atendedor automático quando terminar de criar este atendedor automático.

        > [!Note]
        > O **horário comercial** dos atendedores automáticos aninhados (ou de segundo nível) também será usado, incluindo as chamadas enviadas de outros atendedores automáticos que foram configurados.

<!--    - **call queue** Using a call queue option allows the call to be transferred to an existing call queue that you have set up. -->

* * *

![Número 5](media/sfbcallout5.png)

**Discar por nome** Se você escolher essa opção, as pessoas que ligarem para pesquisarem pessoas em sua organização serão habilitadas para a pesquisa de pastas usando a pesquisa de diretório. Você pode selecionar as pessoas que serão listadas como disponíveis ou indisponíveis para Discagem por Nome na página **Escopo de discagem**. Qualquer usuário online com uma licença de **Sistema de Telefonia** ou hospedado no local usando o Skype for Business Server 2015 ou o Lync Server 2013 pode ser encontrado com a Discagem por Nome.


* * *

Quando terminar de selecionar as opções, clique em **Avançar**.

#### <a name="holiday-call-settings"></a>Configurações de chamadas de Natal

Você pode adicionar até 20 feriados agendados para cada atendedor automático.

> [!TIP]
> Você pode ir à tela em**feriados** de **configurações** > de toda a organização para criar feriados ou pode criá-las como parte da criação de um novo manipulador de chamadas.

![Configurar feriados no atendedor automático](media/50a5ce88-7f39-4210-808a-da7ced969854.png)

![Número 1](media/sfbcallout1.png)

Se você já tiver criado outros atendedores automáticos, talvez veja uma opção que pode ser usada ou editada no que você precisa na lista. Caso contrário, você precisará criar um novo manipulador de chamadas.

Para adicionar um novo manipulador de chamadas, clique em **+ novo manipulador de chamadas**.

* * *

![Configurar feriados em atendedor automático continuado](media/50a5ce88-7f39-4210-808a-da7ced969854b.png)

![Número 1](media/sfbcallout1.png)

Na nova janela, insira um nome para seu novo manipulador de chamadas na parte superior da tela.

![Número 2](media/sfbcallout2.png)

Se o nome do seu feriado já existir na lista suspensa de **feriados** , você poderá usá-lo. Se o nome do feriado que você precisa ainda não existir, selecione **criar novo feriado** na lista suspensa e atribua um nome e uma data para o novo feriado na nova tela exibida. Clique em **salvar** quando estiver pronto.

Os nomes de feriados podem ter até 64 caracteres e devem ser únicos para o mesmo atendedor automático. Por exemplo, você não pode ter dois feriados com o nome "Ação de Graças" no mesmo atendedor automático.

![Número 3](media/sfbcallout3.png)

**Saudação** A saudação é opcional e pode ser definida como **sem saudação**. Nesse caso, a pessoa que liga não ouvirá nenhuma mensagem ou saudação antes da chamada ser atendida por uma das opções selecionadas. Você também pode carregar um arquivo de áudio (em formatos .wav, .mp3 ou. wma) ou criar uma saudação personalizada usando conversão de texto em fala.

- **Sem saudação** Nenhuma saudação será reproduzida quando as pessoas ligarem para o número de telefone do atendedor automático.
- **Carregar um arquivo de áudio** Se você escolher esta, grave a saudação de Natal e, em seguida, carregue o arquivo de áudio (nos formatos. wav,. mp3 ou. WMA)
- **Digite uma mensagem de saudação** Se você escolher essa opção, insira o texto que deseja que o sistema Leia (até 1000 caracteres). Por exemplo, você pode inserir "Feliz ano novo! Nossos escritórios estão fechados no momento." na caixa **digite uma mensagem de saudação** .

![Número 4](media/sfbcallout4.png)

**Ação** Você pode selecionar o que acontece com as chamadas que chegam durante este feriado. Você pode escolher entre as seguintes opções:

- **Desconectar** A pessoa será desconectada após ouvir a saudação de feriado.
- **Redirecionar chamada** Isso pode ser usado para enviar a chamada automaticamente para:
  - Uma **Pessoa da sua empresa** com uma licença de **Sistema de Telefonia** habilitada para Enterprise Voice ou com Planos de Chamadas do Office 365 atribuídos. Você pode configurá-lo para que o chamador possa ser enviado para a caixa postal. Para fazer isso, selecione **pessoa em sua empresa**e defina esta pessoa para que as chamadas sejam encaminhadas diretamente para o correio de voz.

    > [!Note]
    > A **Pessoa da sua empresa** pode ser um usuário Online ou um usuário hospedado no local usando o Skype for Business Server 2015 ou o Lync Server 2013. 

  - Uma **fila de chamadas** para transferir a chamada para uma fila de chamadas existente que você configurou.
  - Outro **atendedor automático**para criar um segundo nível de opções de menu contendo um submenu. These are called nested auto attendants.

    > [!Note]
    > Por padrão, todas as chamadas recebidas durante um período de feriado desconectam a pessoa após a saudação (se houver uma), portanto, você deve especificar um redirecionamento caso outro comportamento seja desejado.

#### <a name="select-dial-scope-page"></a>Página Selecionar escopo de discagem

Nesta página, você pode configurar quais usuários em sua organização serão listados em seu diretório e disponíveis para discar por nome quando uma pessoa ligar para a sua organização.

![Dial scope for searching with dial by name.](media/1bcb185c-00db-43a7-b5c4-9b021c0627f7.png)

* * *

![Número 1](media/sfbcallout1.png) usando a opção **incluir** , você tem duas opções:

- **Todos os usuários online** O uso dessa opção permite que todas as pessoas da organização sejam incluídas na pesquisa do diretório. Todos os usuários Online com uma licença de **Sistema de Telefonia**, bem como os usuários hospedados no local que usam o Skype for Business Server 2015 ou o Lync Server 2013, que têm Planos de Chamadas no Office 365, serão listados.
- **Grupo de usuários personalizado** Se você usar essa opção, poderá pesquisar um grupo, uma lista de distribuição ou um grupo de segurança do Office 365 que tenha sido criado em sua organização e as pessoas adicionadas a este grupo do Office 365, lista de distribuição ou grupo de segurança que sejam **usuários online com um Licença do sistema de telefone** ou hospedada no local usando o Skype for Business server 2015 ou o Lync server 2013. Você pode adicionar vários grupos do Office 365, listas de distribuição e grupos de segurança.

* * *

![Número 2](media/sfbcallout2.png)

Usando a opção **excluir** , você tem duas opções:

- **Nenhuma** O uso desta opção indicará que nenhum usuário online será excluído da pesquisa de diretório.
- **Grupo de usuários personalizado** Se você usar essa opção, poderá pesquisar um grupo, uma lista de distribuição ou um grupo de segurança do Office 365 que tenha sido criado em sua organização, e todas as pessoas adicionadas a este grupo do Office 365, lista de distribuição ou grupos de segurança serão excluídas da pesquisa de diretório. Você pode adicionar vários grupos do Office 365, listas de distribuição e grupos de segurança.

> [!NOTE]
> Pode levar até 36 horas para que um novo usuário tenha o nome listado no diretório quando alguém usa discar por nome com reconhecimento de fala.

Depois de inserir todos os campos obrigatórios e configurar os menus e as opções de manipulação de chamadas, clique em **Enviar**.

## <a name="editing-and-testing-auto-attendants"></a>Editando e testando atendedores automáticos

Depois de ter salvo o atendedor automático, ele será listado na página **Atendedores automáticos**. Isso permitirá que você veja rapidamente algumas das opções que você configurou, incluindo o nome, o número de telefone, o idioma e o status.

Se você quiser fazer alterações em um atendedor automático, selecione o atendedor automático e, no painel Ação, clique em **Editar**.

Você também pode fazer uma chamada de teste rapidamente para o atendedor automático usando o botão **testar** no painel ação.

## <a name="want-to-know-more"></a>Deseja saber mais?

Você também pode usar o Windows PowerShell para criar e configurar atendedores automáticos.

### <a name="auto-attendant-cmdlets"></a>Cmdlets de atendedores automáticos

Veja os cmdlets necessários para gerenciar um atendedor automático.

- [New-CsAutoAttendant](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant?view=skype-ps)  
- [Set-CsAutoAttendant](https://docs.microsoft.com/powershell/module/skype/set-csautoattendant?view=skype-ps) 
- [Get-CsAutoAttendant](https://docs.microsoft.com/powershell/module/skype/get-csattendant?view=skype-ps) 
- [Get-CsAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/get-csautoattendantholidays?view=skype-ps) 
- [Remove-CsAutoAttendant](https://docs.microsoft.com/powershell/module/skype/remove-csautoattendant?view=skype-ps) 
- [New-CsAutoAttendantMenu](https://docs.microsoft.com/powershell/module/skype/new-csautoattendantmenu?view=skype-ps) 
- [New-CsOnlineAudioFile](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineAudioFile?view=skype-ps) 
- [New-CsAutoAttendantCallFlow](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallFlow?view=skype-ps) 
- [Export-CsAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/export-Export-CsAutoAttendantHolidays?view=skype-ps) 
- [New-CsOnlineTimeRange](https://docs.microsoft.com/powershell/module/skype/new-New-CsOnlineTimeRange?view=skype-ps) 
- [New-CsOnlineDateTimeRange](https://docs.microsoft.com/powershell/module/skype/new-csonlinedatetimerange?view=skype-ps) 
- [New-CsOnlineSchedule](https://docs.microsoft.com/powershell/module/skype/New-CsOnlineSchedule?view=skype-ps) 
- [Get-CsAutoAttendantSupportedTimeZone](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone?view=skype-ps)
- [New-CsAutoAttendantCallHandlingAssociation](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation?view=skype-ps)
- [Get-CsAutoAttendantSupportedLanguage](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage?view=skype-ps)
- [Import-CsAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/import-csautoattendantholidays?view=skype-ps) 
- [New-CsAutoAttendantCallableEntity](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallableEntity?view=skype-ps) 

### <a name="more-about-windows-powershell"></a>Mais sobre o Windows PowerShell

- O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 e o Microsoft Teams usando um único ponto de administração que pode simplificar seu trabalho diário, quando você tem várias tarefas para fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:

  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [Por que você precisa usar o PowerShell do Office 365](https://docs.microsoft.com/en-us/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade apenas usando o centro de administração do Microsoft 365, como quando você está usando alterações de configuração para muitos usuários de uma só vez. Saiba mais sobre essas vantagens nos seguintes tópicos:

  - [Gerenciar o Office 365 com o Office 365 PowerShell](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [Usar o Windows PowerShell para gerenciar o Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a>Tópicos relacionados

[Veja aqui o que você obtém com o Sistema de Telefonia no Office 365](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[Obter números de telefone de serviço](/microsoftteams/getting-service-phone-numbers)

[Disponibilidade de audioconferência e planos de chamadas por país e região](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

[New-CsOrganizationalAutoAttendant](https://docs.microsoft.com/en-us/powershell/module/skype/new-csorganizationalautoattendant?view=skype-ps)  

[Quais são os atendedores automáticos do Cloud?](what-are-phone-system-auto-attendants.md)

[Exemplo de pequenas empresas - Configurar um atendedor automático](/microsoftteams/tutorial-org-aa)  
