---
title: Configurar um atendedor automático para Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: 6fc2687c-0abf-43b8-aa54-7c3b2a84b67c
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
description: Saiba como configurar e testar atendedores automáticos para grandes organizações no Microsoft Teams.
ms.openlocfilehash: 5f4b4f21f2e1cca8c8bbc350541cdd861b1bda3f
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674363"
---
# <a name="set-up-an-auto-attendant"></a>Configurar um atendedor automático

Os atendedores automáticos permitem que as pessoas liguem para sua organização e naveguem por um sistema de menus para falar com o departamento certo, fila de chamadas, pessoa ou operador. Você pode criar atendedores automáticos para sua organização com o Microsoft Teams de administração ou com o PowerShell.

> [!TIP]
> Este artigo é para grandes organizações. Se sua organização for uma pequena empresa, leia [Configurar um atendedor automático – tutorial de pequenas](/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb) empresas.

Verifique se você leu [o Plano para Teams atendedores automáticos e filas](plan-auto-attendant-call-queue.md) de chamadas e seguiu as [](plan-auto-attendant-call-queue.md#getting-started) etapas de introdução antes de seguir os procedimentos neste artigo.

Os atendedores automáticos podem direcionar chamadas, com base na entrada dos chamadores, para um dos seguintes destinos: <a name="call-routing-options" ></a>

- **Operador** – o operador definido para o atendedor automático. Definir um operador é opcional. O operador pode ser definido como qualquer um dos outros destinos nesta lista.
- **Pessoa na organização –** uma pessoa em sua organização que pode receber chamadas de voz. Essa pessoa pode ser um usuário online ou um usuário hospedado localmente usando Skype for Business Server.
- **Aplicativo de voz** – outro atendedor automático ou uma fila de chamadas. (Escolha a conta de recurso associada ao atendedor automático ou fila de chamadas ao escolher esse destino.)
- **Caixa** postal – a caixa postal associada a um grupo Microsoft 365 que você especificar. Você pode escolher se deseja transcrições de caixa postal e "Deixe uma mensagem após o tom". prompt do sistema.
- **Número de telefone externo** - qualquer número de telefone. (Consulte [detalhes técnicos de transferência externa](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)).
- **Comunicado (arquivo de áudio)** – Reproduzir um arquivo de áudio. Uma mensagem de anúncio gravada que você carrega salva como áudio em . WAV, .MP3 ou . Formato WMA. A gravação não pode ser maior que 5 MB. O sistema reproduz o comunicado e, em seguida, retorna ao menu atendedor automático.
- **Comunicado (Digitado)** – digite uma mensagem. Texto que você deseja que o sistema leia. Você pode inserir até 1000 caracteres. O sistema reproduz o comunicado e, em seguida, retorna ao menu atendedor automático.

Você será solicitado a escolher uma dessas opções em vários estágios ao configurar um atendedor automático.

Para configurar um atendedor automático, no centro de administração Teams **, expanda** Voz, selecione **Atendedores automáticos** e, em seguida, **selecione Adicionar**.

## <a name="video-demonstration"></a>Demonstração em vídeo

Este vídeo mostra um exemplo básico de como criar um atendedor automático no Teams.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWEnCG?autoplay=false]

## <a name="general-info"></a>Informações gerais

![Captura de tela das configurações do atendedor automático para nome, operador, fuso horário, idioma e entradas de voz.](media/auto-attendant-general-info-page-new.png)

1. Digite um nome para o atendedor automático na caixa na parte superior.

2. Para designar um operador, especifique o destino para chamadas ao operador. Essa designação é opcional (mas recomendada). Defina **a opção** Operador para permitir que os chamadores interrompam os menus e conversem com uma pessoa designada.

3. Especifique o fuso horário para esse atendedor automático. O fuso horário será usado para calcular o horário comercial se você [criar um fluxo de chamada separado para horas extras](#call-flow-for-after-hours).

4. [Especifique um idioma com suporte](create-a-phone-system-auto-attendant-languages.md) para esse atendedor automático. Esse é o idioma que será usado para prompts de voz gerados pelo sistema.

5. Escolha se deseja habilitar entradas de voz. Quando habilitado, o nome de cada opção de menu se torna uma palavra-chave de reconhecimento de fala. Por exemplo, os chamadores podem dizer "Um" para selecionar a opção de menu mapeada para a tecla 1 ou podem dizer "Vendas" para selecionar a opção de menu chamada "Vendas".

   > [!NOTE]
   > Se você escolher um idioma na Etapa 4 que não dá suporte a entradas de voz, essa opção será desabilitada.

6. Selecione **Avançar**.

## <a name="call-flow"></a>Fluxo de chamadas

![Captura de tela das configurações de mensagem de saudação.](media/auto-attendant-call-flow-greeting-message.png)

Escolha se deseja reproduzir uma saudação quando o atendedor automático atender uma chamada.

Se você selecionar **Reproduzir um arquivo de áudio**, poderá usar  o botão Upload arquivo para carregar uma mensagem de saudação gravada salva como áudio em . WAV, .MP3 ou . Formato WMA. A gravação não pode ser maior que 5 MB.

Se você selecionar **Digitar uma mensagem** de saudação, o sistema lerá o texto que você digitar (até 1000 caracteres) quando o atendedor automático atender uma chamada.

![Captura de tela das configurações de roteamento de chamadas.](media/auto-attendant-call-flow-route-call-message.png)

Escolha como você deseja rotear a chamada.

Se você selecionar **Desconectar**, o atendedor automático desligará a chamada.

Se você selecionar **Redirecionar chamada**, poderá escolher um dos destinos de roteamento de chamadas.

Se você selecionar **opções de menu** Reproduzir, poderá optar por  Reproduzir um arquivo de áudio ou Digitar uma mensagem de saudação e, em seguida, escolher entre as opções de menu e **a** pesquisa de diretório.

### <a name="menu-options"></a>Opções de menu

![Captura de tela das opções de tecla de discagem.](media/auto-attendant-call-flow-menu-options-complete.png)

Para opções de discagem, atribua as teclas de 0 a 9 no teclado telefônico a um dos destinos de roteamento de chamadas. (As chaves \* (asterisco) e \# (libra) são reservados pelo sistema e não podem ser reatribuídos. Pressionar qualquer uma dessas teclas repetirá o menu atual.)

> [!NOTE]
> A tecla #só faz backup para o atendedor automático mais recente. Depois que o limite for cruzado para um novo atendedor automático, a tecla # não poderá levá-lo até o anterior.

Mapeamentos de chave não precisam ser contínuos. É possível criar um menu com as teclas 0, 1 e 3 mapeadas para opções, enquanto a tecla número 2 não é usada.

Recomendamos mapear a chave zero para o operador se você tiver configurado uma. Se o operador não estiver definido como nenhuma chave, o comando de voz "Operador" também será desabilitado.

Para cada opção de menu, especifique as seguintes configurações:

- **Tecla de** discagem – a chave no teclado do telefone para acessar essa opção. Se houver entradas de voz disponíveis, os chamadores também poderão dizer esse número para acessar a opção.

- **Comando de** voz – define o comando de voz que um chamador pode dar para acessar essa opção, se as entradas de voz estão habilitadas. Ele pode conter várias palavras, como "Atendimento ao Cliente" ou "Operações e Motivos". Por exemplo, o chamador pode pressionar 2, dizer "dois" ou dizer "Vendas" para selecionar a opção mapeada para as duas teclas. Esse texto também é renderizado por conversão de texto em fala para o prompt de confirmação do serviço, que pode ser algo como "Transferindo sua chamada para vendas".

- **Redirecionar para** – o destino de roteamento de chamadas usado quando os chamadores escolhem essa opção. Se você estiver redirecionando para um atendedor automático ou fila de chamadas, escolha a conta de recurso associada a ela.

### <a name="directory-search"></a>Pesquisa de diretório

Se você atribuir chaves de discagem a destinos, recomendamos que você escolha **Nenhuma** para **pesquisa de diretório**. Se um chamador tentar discar um nome ou extensão usando chaves atribuídas a destinos específicos, ele poderá ser roteado inesperadamente para um destino antes de terminar de inserir o nome ou a extensão. Recomendamos que você crie um atendedor automático separado para pesquisa de diretório e tenha o link principal do atendedor automático com uma chave de discagem.

Se você não atribuiu chaves de discagem, escolha uma opção para pesquisa **de diretório**.

**Discar por nome** – Se você habilitar essa opção, os chamadores poderão dizer o nome do usuário ou digitá-lo no teclado do telefone. Qualquer usuário online ou qualquer usuário hospedado localmente usando o Skype for Business Server, é um usuário qualificado e pode ser encontrado com o Dial por nome. (Você pode definir quem é e não está incluído no diretório na página de escopo [do Dial](#dial-scope) .)

**Discar por extensão** – se você habilitar essa opção, os chamadores poderão se conectar com os usuários em sua organização discando sua extensão de telefone. Qualquer usuário online ou qualquer usuário hospedado localmente usando o Skype for Business Server, é um usuário qualificado e pode ser encontrado com **o Dial por extensão**. (Você pode definir quem é e não está incluído no diretório na página de escopo [do Dial](#dial-scope) .)

Os usuários que você deseja disponibilizar para o Dial By Extension precisam ter uma extensão especificada como parte de um dos seguintes atributos de telefone definidos no Active Directory (e sincronizados via Azure AD Conexão) ou Azure Active Directory. (Consulte [Adicionar usuários individualmente ou em massa](/microsoft-365/admin/add-users/add-users) para obter mais informações.)

- OfficePhone/TelephoneNumber (AD e Azure AD)
- HomePhone (AD)
- Mobile/MobilePhone (AD e Azure AD)
- OtherTelephone (AD)

O formato necessário para inserir a extensão no campo número de telefone do usuário pode ser um dos seguintes formatos:

- *+\<phone number>;ext=\<extension>*
- *+\<phone number>X\<extension>*
- *X\<extension>*

- Exemplo 1: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+15555555678;ext=5678"
- Exemplo 2: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+15555555678x5678"
- Exemplo 3: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "x5678"

Você pode definir a extensão [no Centro de administração do Microsoft 365 ou](https://admin.microsoft.com/) no [Azure Active Directory de administração](https://aad.portal.azure.com). Pode levar até 12 horas para que as alterações estejam disponíveis para atendedores automáticos e filas de chamadas.

> [!NOTE]
> Se você quiser usar os recursos Discar por nome e  Discar por extensão, poderá atribuir uma tecla de discagem no atendedor automático principal para acessar um atendedor automático habilitado para Discar **por nome**. Dentro desse atendedor automático, você pode atribuir a tecla 1 (que não tem letras associadas a ela) para alcançar o atendedor automático **de** discagem por extensão.

Consulte o [Dial e a referência de voz](dial-voice-reference.md) para obter mais informações.

Depois de selecionar uma opção **de pesquisa de** diretório, selecione **Avançar**.

## <a name="call-flow-for-after-hours"></a>Fluxo de chamadas para horas extras

![Captura de tela das configurações de dia e hora após o horário.](media/auto-attendant-business-hours.png)

O horário comercial pode ser definido para cada atendedor automático. Se os horários comerciais não forem definidos, todos os dias e todas as horas do dia serão considerados horários comerciais, porque um cronograma 24/7 é definido por padrão. O horário comercial pode ser definido com intervalos no tempo durante o dia e todas as horas que não estão definidas como horas comerciais são consideradas após o horário comercial. Você pode definir diferentes opções de tratamento de chamadas de entrada e saudações para o horário de expediente.

Dependendo de como você configurou seus atendedores automáticos e filas de chamadas, talvez seja necessário especificar apenas o roteamento de chamadas após o horário comercial para atendedores automáticos com números de telefone diretos.

Se você quiser roteamento de chamadas separado para chamadores após o horário comercial, especifique seu horário comercial para cada dia. Selecione **Adicionar novo horário** para especificar vários conjuntos de horas para um determinado dia, por exemplo, para especificar uma pausa de almoço.

Depois de especificar seu horário comercial, escolha as opções de roteamento de chamadas para horas extras. As mesmas opções estão disponíveis para o roteamento de chamadas de horário comercial especificado acima.

Selecione **Avançar** quando terminar.

## <a name="call-flows-during-holidays"></a>Fluxos de chamadas durante feriados

![Captura de tela das configurações de saudação de feriados e feriados.](media/auto-attendant-holiday-greeting.png)

O atendedor automático pode ter um fluxo de chamada para cada [Feriado que você configurou](set-up-holidays-in-teams.md). Você pode adicionar até 20 feriados agendados para cada atendedor automático.

1. Na página configurações de chamada de Feriado, selecione **Adicionar**.

2. Digite um nome para essa configuração de feriado.

3. Na lista **suspensa** Feriado, escolha o feriado que você deseja usar.

4. Escolha o tipo de saudação que você deseja usar.

    ![Captura de tela das configurações de ação de chamada de feriado.](media/auto-attendant-holiday-actions.png)

5. Escolha se deseja **desconectar**, **redirecionar** ou **reproduzir opções de menu**.

6. Se você optar por redirecionar, escolha o destino de roteamento de chamadas para a chamada.

7. Se você optar por reproduzir opções de menu, configure as [opções de menu](#menu-options).

8. Selecione **Salvar**.

![Captura de tela das configurações de feriados com feriados listados.](media/auto-attendant-holiday-call-settings.png)

Repita o procedimento conforme necessário para cada feriado adicional.

Quando você tiver adicionado todos os seus feriados, selecione **Avançar**.

## <a name="dial-scope"></a>Escopo de discagem

![Captura de tela das opções de inclusão e exclusão do escopo de discagem.](media/auto-attendant-dial-scope.png)

O *escopo de* discagem define quais usuários estão disponíveis no diretório quando um chamador usa discagem por nome ou discagem por extensão. O padrão de **Todos os usuários online** inclui todos os usuários em sua organização que são usuários online ou hospedados localmente usando Skype for Business Server.

Você pode incluir ou excluir usuários específicos selecionando o grupo de  usuários personalizado  em Incluir ou Excluir e escolhendo um ou mais grupos de Microsoft 365, listas de distribuição ou grupos de segurança. Por exemplo, talvez você queira excluir executivos em sua organização do diretório de discagem. (Se um usuário estiver em ambas as listas, ele será excluído do diretório.)

> [!NOTE]
> Pode levar até 36 horas para que um novo usuário tenha seu nome listado no diretório.

Quando terminar de definir o escopo de discagem, selecione **Avançar**.

## <a name="resource-accounts"></a>Contas de recursos

Todos os atendedores automáticos devem ter uma conta de recurso associada.  Os atendedores automáticos de primeiro nível precisarão de pelo menos uma conta de recurso que tenha um número de serviço associado. Se desejar, você pode atribuir várias contas de recurso a um atendedor automático, cada uma com um número de serviço separado.

![Captura de tela do painel Adicionar contas da conta de recurso.](media/auto-attendant-add-resource-account.png)

Para adicionar uma conta de recurso, **selecione Adicionar conta** e pesquise a conta que você deseja adicionar. Selecione **Adicionar** e, em seguida, **selecione Adicionar**.

![Captura de tela da lista de contas de recursos mostrando a conta de recurso com o número de serviço atribuído.](media/auto-attendant-resource-account-assigned.png)

Quando terminar de adicionar contas de recursos, selecione **Enviar para** concluir a configuração do atendedor automático.

Consulte [Gerenciar Teams de recursos para](manage-resource-accounts.md) obter mais informações.

## <a name="external-phone-number-transfers---technical-details"></a>Transferências de número de telefone externo – detalhes técnicos

Consulte os [Pré-requisitos para](plan-auto-attendant-call-queue.md#prerequisites) permitir que os atendedores automáticos transfira chamadas externamente.  Além disso:

- Para uma conta de recurso com [](calling-plans-for-office-365.md) uma licença de Plano de Chamada [ou](operator-connect-plan.md) um número de Conexão do operador, o número de telefone de transferência externa deve ser inserido no formato E.164 (+[código do país][código de área][número de telefone]).

- Para uma conta de recurso com uma política de roteamento de voz online de Licença Telefonia do Microsoft Teams e Roteamento Direto, o formato de número de telefone de transferência externa depende das configurações do Controlador de Borda de Sessão [(SBC](direct-routing-connect-the-sbc.md)).

O número de telefone de saída exibido é determinado da seguinte maneira:

  - Para o Plano de Chamadas e Conexão do operador números, o número de telefone do chamador original é exibido.
  - Para números de Roteamento Direto, o número enviado baseia-se na configuração de PAI (identidade P-Asserted-Identity) no SBC, da seguinte maneira:
    - Se definido como Desabilitado, o número de telefone do chamador original será exibido. Essa é a configuração padrão e recomendada.
    - Se definido como Habilitado, o número de telefone da conta de recurso será exibido.

Em um Skype for Business híbrido, para transferir uma chamada de atendedor automático para o PSTN, crie um novo usuário local com o encaminhamento de chamadas definido como o número PSTN. O usuário deve estar habilitado para Enterprise Voice e ter uma política de voz atribuída. Para saber mais, confira [Transferência de chamada de atendedor automático para PSTN](/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn).

## <a name="auto-attendant-cmdlets"></a>Cmdlets de atendedores automáticos

Windows PowerShell permite criar e gerenciar atendedores automáticos por meio da linha de comando de maneira programática ou em lote.

Os cmdlets a seguir permitem que você gerencie atendedores automáticos:

- [New-CsAutoAttendant](/powershell/module/skype/new-csautoattendant)  
- [Get-CsAutoAttendant](/powershell/module/skype/get-csautoattendant)
- [Set-CsAutoAttendant](/powershell/module/skype/set-csautoattendant)
- [Update-CsAutoAttendant](/powershell/module/skype/update-csautoattendant)
- [Remove-CsAutoAttendant](/powershell/module/skype/remove-csautoattendant)
- [New-CsOnlineTimeRange](/powershell/module/skype/new-csonlinetimerange)
- [New-CsOnlineDateTimeRange](/powershell/module/skype/new-csonlinedatetimerange)
- [New-CsOnlineSchedule](/powershell/module/skype/New-CsOnlineSchedule)
- [Get-CsAutoAttendantHolidays](/powershell/module/skype/get-csautoattendantholidays)
- [Import-CsAutoAttendantHolidays](/powershell/module/skype/import-csautoattendantholidays)
- [Export-CsAutoAttendantHolidays](/powershell/module/skype/export-csautoattendantholidays)
- [New-CsAutoAttendantDialScope](/powershell/module/skype/New-CsAutoAttendantDialScope)
- [New-CsAutoAttendantPrompt](/powershell/module/skype/New-CsAutoAttendantPrompt)
- [New-CsAutoAttendantCallableEntity](/powershell/module/skype/New-CsAutoAttendantCallableEntity)
- [New-CsAutoAttendantMenuOption](/powershell/module/skype/New-CsAutoAttendantMenuOption)
- [New-CsAutoAttendantMenu](/powershell/module/skype/new-csautoattendantmenu)
- [New-CsAutoAttendantCallFlow](/powershell/module/skype/New-CsAutoAttendantCallFlow)
- [New-CsAutoAttendantCallHandlingAssociation](/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation)
- [Get-CsAutoAttendantStatus](/powershell/module/skype/Get-CsAutoAttendantStatus)
- [Get-CsAutoAttendantTenantInformation](/powershell/module/skype/Get-CsAutoAttendantTenantInformation)

Os seguintes cmdlets adicionais também são necessários para gerenciar os usuários, contas de recursos, licenças do Telefonia do Microsoft Teams, números de telefone, arquivos de áudio e idioma com suporte que serão usados com filas de chamadas:

Usuários/Teams

- Usuários
- - [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser)

- Teams: 
- - [Get-Team](/powershell/module/teams/Get-Team)

Contas de recursos:

- [New-CsOnlineApplicationInstance](/powershell/module/skype/New-CsOnlineApplicationInstance)
- [Find-CsOnlineApplicationInstance](/powershell/module/skype/Find-CsOnlineApplicationInstance)
- [Get-CsOnlineApplicationInstance](/powershell/module/skype/Get-CsOnlineApplicationInstance)
- [Set-CsOnlineApplicationInstance](/powershell/module/skype/Set-CsOnlineApplicationInstance)
- [New-CsOnlineApplicationInstanceAssociation](/powershell/module/skype/New-CsOnlineApplicationInstanceAssociation)
- [Get-CsOnlineApplicationInstanceAssociation](/powershell/module/skype/Get-CsOnlineApplicationInstanceAssociation)
- [Remove-CsOnlineApplicationInstanceAssociation](/powershell/module/skype/Remove-CsOnlineApplicationInstanceAssociation)
- [Get-CsOnlineApplicationInstanceAssociationStatus](/powershell/module/skype/Get-CsOnlineApplicationInstanceAssociationStatus)

Licenças Teams Telefone virtual:

- [Get-MsolAccountSku](/powershell/module/msonline/get-msolaccountsku)
- [Set-MsolUserLicense](/powershell/module/msonline/set-msoluserlicense)

Telefone atribuição de número:

- [Get-CsOnlineTelephoneNumber](/powershell/module/skype/Get-CsOnlineTelephoneNumber)
- [Set-CsPhoneNumberAssignment](/powershell/module/teams/Set-CsPhoneNumberAssignment)

Arquivos de Áudio

- [Get-CsOnlineAudioFile](/powershell/module/skype/Get-CsOnlineAudioFile)
- [Import-CsOnlineAudioFile](/powershell/module/skype/Import-CsOnlineAudioFile)
- [Export-CsOnlineAudioFile](/powershell/module/skype/Export-CsOnlineAudioFile)
- [Remove-CsOnlineAudioFile](/powershell/module/skype/Remove-CsOnlineAudioFile)

Idiomas de suporte e fusos horários

- [Get-CsAutoAttendantSupportedLanguage](/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage)
- [Get-CsAutoAttendantSupportedTimeZone](/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone)

Para obter um guia passo a passo para criar atendedores automáticos com o PowerShell, consulte Criando Atendedores [Automáticos com cmdlets do PowerShell](create-a-phone-system-auto-attendant-via-cmdlets.md)

## <a name="auto-attendant-diagnostic-tool"></a>Ferramenta de Diagnóstico do Atendedor Automático

Se você for um administrador, poderá usar a seguinte ferramenta de diagnóstico para validar se um atendedor automático é capaz de receber chamadas:

1. Selecione **Executar testes** abaixo, o que preencherá o diagnóstico no Centro de Administração do Microsoft 365. 

   > [!div class="nextstepaction"]
   > [Executar testes: Teams Atendedor Automático](https://aka.ms/TeamsAADiag)

2. No painel Executar diagnóstico, insira a Conta de Recurso no campo Nome de Usuário ou **Email** e selecione **Executar Testes**.

3. Os testes identificarão configurações de locatário, política ou conta de recurso que estão impedindo o atendedor automático de receber chamadas e fornecerão etapas para corrigir quaisquer problemas identificados.

## <a name="related-topics"></a>Tópicos relacionados

[Veja o que você obtém com Teams Telefone](./here-s-what-you-get-with-phone-system.md)

[Obter números de telefone de serviço](./getting-service-phone-numbers.md)

[Disponibilidade de Audioconferência e Planos de Chamadas por país e região](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[Uma introdução ao Windows PowerShell e ao Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
