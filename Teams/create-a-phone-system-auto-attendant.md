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
ms.openlocfilehash: 8ab3dd318e8ae4c815a78dcc8f7430b2b6d08b04
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32218787"
---
# <a name="set-up-a-cloud-auto-attendant"></a>Configurar um atendedor automático do Cloud

Atendedores automáticos permitem que as pessoas que ligam para sua organização e navegue para conectá-los ao departamento direita, chame a fila, pessoa ou o operador de um sistema de menus. Você pode criar um atendedor automático para sua organização usando o Centro de administração do Microsoft Teams. Para criar um novo atendedor automático, vá para **voz** no painel de navegação esquerdo e selecione **atendedores automáticos** > **Adicionar novo**.

Se você deseja saber mais sobre os atendedores automáticos, consulte [Cite atendedores automáticos de nuvem?](/microsoftteams/what-are-phone-system-auto-attendants)

> [!NOTE]
> Este artigo se aplica ao Microsoft Teams e Skype para Business Online.



## <a name="step-1---get-started"></a>Etapa 1 - Introdução

- Um atendedor automático é necessário ter uma conta de recurso associado. Consulte [Gerenciar contas de recursos em equipes](manage-resource-accounts.md) para obter detalhes sobre as contas de recursos.
- Se você planeja atribua um número de roteamento direto, você precisará adquirir e atribuir as seguintes licenças às suas contas de recurso \(Office 365 Enterprise E1, E3 ou E5, com o complemento de sistema telefônico\).
- Se você estiver atribuindo um número de serviço da Microsoft em vez disso, você precisará adquirir e atribuir as seguintes licenças à sua conta do recurso \(Office 365 Enterprise E1, E3 ou E5, com o complemento de sistema telefônico e um plano de chamar\).

> [!NOTE] 
> Microsoft está trabalhando em um modelo de licenciamento apropriado para aplicativos como atendedores automáticos de nuvem e filas de chamada, para agora você precisa usar o modelo de licenciamento por usuário.

> [!CAUTION]
> Para obter e usar números de telefone gratuitos, você precisa configurar Créditos de Comunicação. Para fazer isso, consulte [O que são Créditos de Comunicação?](what-are-communications-credits.md) e [Configurar Créditos de Comunicação para a sua organização](set-up-communications-credits-for-your-organization.md).

> [!TIP]
> Para redirecionar chamadas para um operador ou uma opção de menu que é um usuário Online com uma licença de **Sistema telefônico** , você precisará habilitá-los para o Enterprise Voice ou atribuir chamar planos no Office 365 para acessá-los. Consulte [Atribuir Skype para licenças de negócios](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) ou [equipes da Microsoft atribuir licenças](assign-teams-licenses.md). Você também pode usar o Windows PowerShell. Por exemplo, execute:`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

## <a name="step-2---create-a-new-auto-attendant"></a>Etapa 2 - Criar um novo atendedor automático

> [!IMPORTANT]
> Cada atendedor automático é necessário ter uma [conta do recurso](manage-resource-accounts.md)de associada. Você deve criar a conta do recurso primeiro, depois você pode associá-lo para o atendedor automático.

### <a name="using-the-microsoft-teams-admin-center"></a>Usando o Centro de administração do Microsoft Teams

No **Centro de administração de equipes da Microsoft**, clique em **voz** > **atendedores automáticos**, clique em **+ novo**:

#### <a name="general-info-page"></a>Página de informações gerais

![New auto attendant page 1.](media/edacec94-9384-4a87-be0a-5c49a151287e.png)

* * *

![Número 1](media/sfbcallout1.png)

**Nome** Insira um nome de exibição descritivo para o atendedor automático. O nome é obrigatório e pode conter até 64 caracteres, incluindo espaços. Ele será listado na coluna **Nome** da guia **Atendedores automáticos**.

* * *

![Número 2](media/sfbcallout2.png)

**Conta do recurso** Clique nesse botão para selecionar uma ou mais contas de recurso para se conectar ao seu novo atendedor automático. Todos os atendedores automáticos de são necessários para ter uma conta de recurso associado. Uma conta de recurso pode ter um número de telefone associado à conta, mas talvez não. Um atendedor automático de nível superior geralmente têm uma conta de recurso com um número de telefone atribuído, mas AutoAttendant aninhados (usado como um menu de nível 2 que o atendedor automático de nível da primeiro conecta-se à) pode não ter um número de telefone atribuído a sua conta do recurso.

* * *

![Número 3](media/sfbcallout3.png)

**Fuso horário** Você deve definir o fuso horário para o atendedor automático, mas ele não precisa corresponder ao fuso horário do endereço principal de sua organização. Cada atendedor automático pode ter um fuso horário diferente e os horários comerciais definidos para o atendedor automático serão definidos com base no fuso horário que você selecionar aqui.

* * *

![Número 4](media/sfbcallout4.png)

**Idioma** Selecione o idioma que você deseja usar para o atendedor automático entre os idiomas disponíveis listados. O idioma que você definir aqui é o idioma que o atendedor automático usará para interagir com pessoas que ligam para este atendedor automático e todo os sistema os avisos serão reproduzidos neste idioma.

* * *

![Número 5](media/sfbcallout5.png)

**Operador** Isso é opcional e não precisa ser definido para o atendedor automático. No entanto, você pode definir a opção de **operador** para pessoas que ligam para ser capaz de quebrar sem os menus para falar com uma pessoa para ajudá-los.

A tecla 0 é atribuída automaticamente ao Operador.

Se você configurar isso, você também precisará informar as pessoas a quem chamar que isso é uma opção disponível em **Opções de menu de edição** , na página de **tratamento de chamada do horário comercial** . Se você definir um operador na sua atendedor automático, você precisará inserir o texto de aviso correspondente na caixa **os chamadores ouvirão** ou alterar seu arquivo de áudio para incluir essa opção. Por exemplo, "Para falar com o operador, pressione 0".

Você pode definir um dos seguintes como Operador:

- **Pessoa da sua empresa** com uma licença de **Sistema de Telefonia** habilitada para Enterprise Voice ou com Planos de Chamadas do Office 365 atribuídos.

     > [!Note]
     > A **Pessoa da sua empresa** pode ser um usuário Online ou um usuário hospedado no local usando o Skype for Business Server 2015 ou o Lync Server 2013.

- Uma **fila de chamadas** que você definiu.
- Você pode configurá-lo para que a pessoa que liga seja enviada para a caixa postal. Para fazer isso, selecione **a pessoa da sua empresa** e defina as chamadas sejam encaminhadas diretamente para a caixa postal dessa pessoa.

* * *

![Número 6](media/sfbcallout6.png)

**Habilitar entradas de voz** Reconhecimento de fala está disponível se esta opção está selecionada. Pessoas que chamam no podem usar a entrada de voz no [idioma definido](set-auto-attendant-languages-for-audio-conferencing-in-teams.md). Você pode desativar o reconhecimento de fala, definindo-la como desativado, se você quiser apenas permitir que as pessoas usam do teclado do telefone.

* * *

Quando você terminar com suas seleções, clique em **Avançar**.

#### <a name="business-hours-page"></a>Página de horário comercial

Por padrão, o horário comercial é definido para 9 am a 17: 00, de segunda à sexta-feira.  Todos os horários que não estão incluídos nos horários comerciais são considerados horários fora do expediente. Você pode clicar em **Selecione 24/7** para tornar todos os horários de expediente. A menos que você selecione a opção **Select 24/7** , a página **depois de configurações de chamadas de horas** será usada para configurar a tratamento de chamadas para após o horário comercial para o atendedor automático.

![New auto attendant Hours of operation.](media/61769547-cdb4-45c0-af5a-3d6e0731fbc6.png)

* * *

![Número 1](media/sfbcallout1.png)

Por padrão, o horário comercial é definido de segunda à sexta-feira, das 9:00 am - 5:00 pm. Selecione opção **Limpar todas as horas** para desmarcar todas as horas horários da agenda. Quando você seleciona **Redefinir como padrão**, de segunda à sexta-feira, das 9:00 am - 5:00 pm será redefinido horário comercial.

* * *

![Número 2](media/sfbcallout2.png)

Para alterar os horários comerciais, destaque os horários comerciais que deseja definir usando o calendário. O calendário permite que você selecione horários comerciais em intervalos de 30 minutos, e o horário comercial que você selecionar aqui será definido com base no fuso horário que você definiu na página **Geral info** . Para configurar um intervalo (horário de almoço, por exemplo), desmarque ou arraste para desmarcar o horário no calendário. Você pode definir várias quebras em horário comercial.

* * *

Quando você terminar com suas seleções, clique em **Avançar**.

#### <a name="business-hours-call-settings"></a>Configurações de chamadas do horário comercial

> [!TIP]
> Se você usar uma agenda de horário comercial personalizado, você também precisará configurar uma chamada de manusear para após o horário comercial usando a página **após o horário de tratamento de chamada** , que fornecerá a você as mesmas opções como **configurações de chamadas do horário comercial**.

Você pode configurar saudações e prompts menus que as pessoas que a chamada no número de telefone do atendedor automático da sua organização ouvirá durante o horário comercial.

![Tratamento de chamada do horário comercial. ](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)
 ![Horário comercial continuado de tratamento de chamada.](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8b.png)

* * *

![Número 1](media/sfbcallout1.png)

**Saudação** Uma saudação para horário comercial é opcional e pode ser definida como **Nenhuma saudação**. Nesse caso, o chamador não será ouvida nenhuma mensagem ou saudação antes que a chamada é atendida por uma das ações que você selecionar. Você também pode carregar um arquivo de áudio (em formatos .wav, .mp3 ou. wma) ou criar uma saudação personalizada usando conversão de texto em fala.

- **Nenhum saudação** Nenhum saudação será reproduzida quando as pessoas ligam para o número de telefone do atendedor automático.
- **Carregar um arquivo de áudio** Se você escolher essa opção, gravar a saudação e, em seguida, carregue o seu arquivo de áudio (em um formato. wav,. mp3 ou. wma).
- **Digite uma mensagem de saudação** Se você escolher essa opção, insira o texto que você deseja que o sistema para ler (até 1000 caracteres). Por exemplo, você pode inserir "Bem-vindo à Contoso. A sua ligação é muito importante para nós." na caixa **Os chamadores ouvirão**.

* * *

![Número 2](media/sfbcallout2.png)

Você pode selecionar o que acontece às chamadas que chegam durante o horário comercial. É possível escolher entre as seguintes ações:

- **Desconectar** Se você selecionar a ele, a pessoa chamando em será desconectada depois de ouvir uma saudação para horário comercial.
- **Redirecionar chamada** Isso pode ser usado para enviar a chamada automaticamente para:
  - **Pessoa da empresa** com uma licença de **Sistema telefônico** que está habilitada para Enterprise Voice ou atribuída chamar planos no Office 365. Você pode configurá-lo para que o chamador possa ser enviado para a caixa postal. Para fazer isso, selecione **a pessoa da empresa** e defina essa pessoa para que suas chamadas encaminhadas diretamente para a caixa postal.

    > [!Note]
    > **Pessoa da empresa** pode ser um usuário Online ou um usuário hospedado no local usando Skype para Business Server 2015 ou o Lync Server 2013.

   - Outro **atendedor automático**

   Você pode usar um atendedor automático existente para criar um segundo nível das opções de menu que contém um submenu. These are called nested auto attendants. Para enviar a chamada para um atendedor automático aninhados, selecione a **pessoa na empresa** e atribuir uma conta de recurso, um que já tenha um atendedor automático associado ou um que você irá associar a um atendedor automático depois que terminar criando este atendedor automático.

- **Opções de menu de reprodução** também pode ser usado para permitir que você defina um prompt a que ser reproduzido.

* * *

![Número 3](media/sfbcallout3.png)

**Prompt do menu** Para criar o prompt do menu principal, você pode usar a conversão de texto em fala ou carregar um arquivo de áudio (.wav, .mp3 ou .wma). Você pode digitar o prompt na caixa **definir sua navegação de menu para os chamadores** ou registrar um arquivo de áudio e dizer, por exemplo: "para vendas, diga ou pressione ou dizer 1. Para Serviços, pressione ou fale 2. Para Suporte ao Cliente, pressione ou fale 3. Para falar com o operador, pressione ou fale 0. Para ouvir este menu novamente, pressione a tecla de asterisco ou fale repetir". **Digite uma mensagem de saudação** Se você escolher essa opção, você deve inserir o texto que você deseja que o sistema para ler (até 1000 caracteres). **Carregar um arquivo de áudio** Se você escolher isso, deverá gravar a saudação e depois carregar o arquivo de áudio (nos formatos .wav, .mp3 ou .wma).

* * *

![Número 4](media/sfbcallout4.png)

**Configuração de opções de menu** Opções de menu usando botões de tecla no teclado podem ser adicionadas ou removidas. Para adicionar uma opção de menu, pressione **+ atribuir uma tecla de discagem**. Uma linha correspondente das opções serão exibidos abaixo. Para excluir uma opção de menu, clique no lado esquerdo da chave correspondente no controle do teclado e clique no ícone Excluir acima. A linha de mapeamento de teclas será removida.

> [!TIP]
> Você precisará atualizar o texto de prompts de menu ou gravar novamente o áudio separadamente ao adicionar a removendo opções porque ele não será feito automaticamente para o prompt do menu existente.  
>
>Qualquer opção de menu pode ser adicionada e removida em qualquer ordem, e os mapeamentos de teclas não precisam ser contínuo. Por exemplo, é possível, para criar um menu com as teclas de 0, 1 e 3 mapeadas para opções, enquanto a tecla 2 não será usada.

> [!NOTE]
> As chaves \* (repetir) e \# (novamente) são reservados pelo sistema e não pode ser reatribuído. Se o reconhecimento de fala estiver habilitado, pressionando * corresponderá com "Repetir" e # corresponderá com os comandos de voz "Volta".

Para configurar suas opções de menu, depois de selecionar as teclas de discagem, você precisará:

- Insira o **comando de voz** da opção. Isso pode ter até 64 caracteres de comprimento e pode conter várias palavras como "E atendimento"ao cliente ou"operações pó." Se o reconhecimento de fala está habilitado, o nome será reconhecido automaticamente e a pessoa chamando em poderão Pressione 3, diga "três", ou dizer "Atendimento ao cliente" para selecionar a opção mapeada para a tecla 3.
- Selecione onde a chamada será enviado se a tecla correspondente é pressionada, ou a opção está selecionada usando o reconhecimento de fala. A chamada pode ser enviada para:

  - **Operador** Se operador já estiver configurado, ele é mapeado automaticamente a chave 0, mas ele também pode ser excluído ou reatribuído a uma chave diferente. If operator isn't set to any key, then the voice command "Operator" will be disabled too.
  - Uma **Pessoa da sua empresa** com uma licença de **Sistema de Telefonia** habilitada para Enterprise Voice ou com um Plano de Chamadas do Office 365 atribuído. Você pode configurá-lo para que o chamador possa ser enviado para a caixa postal. Para fazer isso, selecione **a pessoa da sua empresa** e defina essa pessoa para que suas chamadas encaminhadas diretamente para a caixa postal.

    > [!Note]
    > A **Pessoa da sua empresa** pode ser um usuário Online ou um usuário hospedado no local usando o Skype for Business Server 2015 ou o Lync Server 2013. 
    - Outro **atendedor automático**

       Você pode usar um atendedor automático existente para criar um segundo nível das opções de menu que contém um submenu. These are called nested auto attendants. Para enviar a chamada para um atendedor automático aninhados, selecione a **pessoa na empresa** e atribuir uma conta de recurso, um que já tenha um atendedor automático associado ou um que você irá associar a um atendedor automático depois que terminar criando este atendedor automático.

        > [!Note]
        > O **horário comercial** de atendedores automáticos aninhados (ou segundo nível) também será usada, incluindo para as chamadas enviadas a partir de outros atendedores automáticos que foram configurados.

<!--    - **call queue** Using a call queue option allows the call to be transferred to an existing call queue that you have set up. -->

* * *

![Número 5](media/sfbcallout5.png)

**Discagem por nome** Se você escolher essa opção, isso permitirá que as pessoas que ligam para pesquisar por pessoas em uma organização usando a pesquisa de diretório. Você pode selecionar as pessoas que serão listadas como disponíveis ou indisponíveis para Discagem por Nome na página **Escopo de discagem**. Qualquer usuário online com uma licença de **Sistema de Telefonia** ou hospedado no local usando o Skype for Business Server 2015 ou o Lync Server 2013 pode ser encontrado com a Discagem por Nome.


* * *

Quando você terminar com suas seleções, clique em **Avançar**.

#### <a name="holiday-call-settings"></a>Configurações de chamada de feriado

Você pode adicionar até 20 feriados agendados para cada atendedor automático.

> [!TIP]
> Você pode passar a tela em **toda a organização configurações** > **feriados** para criar os feriados ou você pode criá-los como parte da criação de um novo manipulador de chamada.

![Configurar feriados no atendedor automático](media/50a5ce88-7f39-4210-808a-da7ced969854.png)

![Número 1](media/sfbcallout1.png)

Se você já criou outros atendedores automáticos, você poderá ver uma opção que você pode usar ou editar no que você precisa dessa lista. Caso contrário, você precisará criar um novo manipulador de chamada.

Para adicionar um novo manipulador de chamada, clique em **+ novo manipulador de chamada**.

* * *

![Configurando feriados no atendedor automático da continuação](media/50a5ce88-7f39-4210-808a-da7ced969854b.png)

![Número 1](media/sfbcallout1.png)

Na nova janela, insira um nome para seu novo manipulador de chamada na parte superior da tela.

![Número 2](media/sfbcallout2.png)

Se o nome do seu evento já existir na lista suspensa **feriados** , você pode usá-lo. Se o nome do feriado que você precisa ainda não existir, selecione **Criar novo feriado** na lista suspensa e atribua um nome e uma data para o novo feriado na tela do novo que aparece. Clique em **Salvar** quando estiver pronto.

Os nomes de feriados podem ter até 64 caracteres e devem ser únicos para o mesmo atendedor automático. Por exemplo, você não pode ter dois feriados com o nome "Ação de Graças" no mesmo atendedor automático.

![Número 3](media/sfbcallout3.png)

**Saudação** A saudação é opcional e pode ser definida como **Nenhuma saudação**. Nesse caso, a pessoa que liga não ouvirá nenhuma mensagem ou saudação antes da chamada ser atendida por uma das opções selecionadas. Você também pode carregar um arquivo de áudio (em formatos .wav, .mp3 ou. wma) ou criar uma saudação personalizada usando conversão de texto em fala.

- **Nenhum saudação** Nenhum saudação será reproduzida quando as pessoas ligam para o número de telefone do atendedor automático.
- **Carregar um arquivo de áudio** Se você escolher essa opção, gravar a saudação de feriado e, em seguida, carregue o seu arquivo de áudio (em um formato. wav,. mp3 ou. wma)
- **Digite uma mensagem de saudação** Se você escolher essa opção, insira o texto que você deseja que o sistema para ler (até 1000 caracteres). Por exemplo, você pode inserir "Feliz ano novo! Nossos escritórios estão fechados no momento." Na caixa **Digite uma mensagem de saudação** .

![Número 4](media/sfbcallout4.png)

**Ações** Você pode selecionar o que acontece com as chamadas que chegam durante este feriado. Você pode escolher entre as seguintes opções:

- **Desconectar** A pessoa será desconectada após ouvir a saudação de feriado.
- **Redirecionar chamada** Isso pode ser usado para enviar a chamada automaticamente para:
  - Uma **Pessoa da sua empresa** com uma licença de **Sistema de Telefonia** habilitada para Enterprise Voice ou com Planos de Chamadas do Office 365 atribuídos. Você pode configurá-lo para que o chamador possa ser enviado para a caixa postal. Para fazer isso, selecione a **pessoa na sua empresa**e defina essa pessoa para que suas chamadas encaminhadas diretamente para a caixa postal.

    > [!Note]
    > A **Pessoa da sua empresa** pode ser um usuário Online ou um usuário hospedado no local usando o Skype for Business Server 2015 ou o Lync Server 2013. 

  - Uma **fila de chamadas** para transferir a chamada para uma fila de chamada existente que você definiu.
  - Outro **atendedor automático**, para criar um segundo nível das opções de menu que contém um submenu. These are called nested auto attendants.

    > [!Note]
    > Por padrão, todas as chamadas recebidas durante um período de feriado desconectam a pessoa após a saudação (se houver uma), portanto, você deve especificar um redirecionamento caso outro comportamento seja desejado.

#### <a name="select-dial-scope-page"></a>Página Selecionar escopo de discagem

Nesta página, você pode configurar quais usuários em sua organização poderão ser listados no diretório e disponíveis para discagem pelo nome quando uma pessoa que chama em sua organização.

![Dial scope for searching with dial by name.](media/1bcb185c-00db-43a7-b5c4-9b021c0627f7.png)

* * *

![Número 1](media/sfbcallout1.png) usando a opção **incluir** , você tem duas opções:

- **Todos os usuários online** O uso dessa opção permite que todas as pessoas da organização sejam incluídas na pesquisa do diretório. Todos os usuários Online com uma licença de **Sistema de Telefonia**, bem como os usuários hospedados no local que usam o Skype for Business Server 2015 ou o Lync Server 2013, que têm Planos de Chamadas no Office 365, serão listados.
- **Grupo de usuário personalizado** Se você usar essa opção, você pode procurar um grupo do Office 365, lista de distribuição ou grupo de segurança que foi criado em sua organização e as pessoas adicionadas para este grupo do Office 365, lista de distribuição ou grupo de segurança que são um dos **usuários Online com uma Licença do sistema telefônico** ou hospedado no local usando Skype para Business Server 2015 ou o Lync Server 2013. Você pode adicionar vários grupos do Office 365, listas de distribuição e grupos de segurança.

* * *

![Número 2](media/sfbcallout2.png)

Usando a opção **Excluir** , você tem duas opções:

- **Nenhuma** O uso desta opção indicará que nenhum usuário online será excluído da pesquisa de diretório.
- **Grupo de usuário personalizado** Se você usar essa opção, você pode procurar um grupo do Office 365, lista de distribuição ou grupo de segurança que foi criado em sua organização, e todas as pessoas adicionado a esse grupo do Office 365, lista de distribuição ou grupos de segurança serão excluídos da pesquisa de diretório. Você pode adicionar vários grupos do Office 365, listas de distribuição e grupos de segurança.

> [!NOTE]
> Poderá demorar até 36 horas para um novo usuário ter seu nome listado no diretório quando alguém usa discagem pelo nome, com reconhecimento de fala.

Depois de inserir todos os campos necessários e configurar opções e menus de tratamento de chamada, clique em **Enviar**.

## <a name="editing-and-testing-auto-attendants"></a>Edição e testes atendedores automáticos

Depois de ter salvo o atendedor automático, ele será listado na página **Atendedores automáticos**. Isso permitirá que você veja rapidamente algumas das opções que você definiu, incluindo o nome, número de telefone, idioma e status.

Se desejar fazer alterações em um atendedor automático, selecione o atendedor automático e, em seguida, no painel de ações, clique em **Editar**.

Também rapidamente, você pode colocar uma chamada de teste para o atendedor automático usando o botão **Testar** no painel ação.

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

- O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 e Microsoft Teams usando um único ponto de administração que pode simplificar o seu trabalho diário, quando você tem várias tarefas fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:

  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [Por que você precisa usar o PowerShell do Office 365](https://docs.microsoft.com/en-us/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade em relação a usar somente o centro de administração do Office 365, como para fazer alterações de configuração para vários usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos:

  - [Gerenciar o Office 365 com o Office 365 PowerShell](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [Usar o Windows PowerShell para gerenciar o Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a>Tópicos relacionados

[Veja aqui o que você obtém com o Sistema de Telefonia no Office 365](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[Obter números de telefone de serviço](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)

[Disponibilidade de audioconferência e planos de chamadas por país e região](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

[New-CsOrganizationalAutoAttendant](https://docs.microsoft.com/en-us/powershell/module/skype/new-csorganizationalautoattendant?view=skype-ps)  

[Quais são os atendedores automáticos do Cloud?](what-are-phone-system-auto-attendants.md)

[Exemplo de pequenas empresas - Configurar um atendedor automático](https://docs.microsoft.com/skypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa)  
