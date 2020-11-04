---
title: Configurar um atendedor automático para o Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: colongma
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
description: Saiba como configurar e testar atendedores automáticos do Microsoft Teams.
ms.openlocfilehash: ae1863d30236321080fb580e9152f8c3a09d0ad2
ms.sourcegitcommit: 3f465eb6eb46db008f2b69fc4c6bb425d432dfcc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48878187"
---
# <a name="set-up-an-auto-attendant"></a>Configurar um atendedor automático

Os atendedores automáticos permitem que as pessoas liguem para sua organização e naveguem em um sistema de menus para falar com o departamento certo, a fila de chamadas, a pessoa ou um operador. Você pode criar atendedores automáticos para sua organização com o centro de administração do Microsoft Teams ou com o PowerShell. 

Verifique se você leu o [plano de atendedores automáticos e filas de chamadas do teams](plan-auto-attendant-call-queue.md) e seguiu as [etapas de introdução](plan-auto-attendant-call-queue.md#getting-started) antes de seguir os procedimentos deste artigo.

Os atendedores automáticos podem direcionar chamadas com base nas entradas dos chamadores para um dos seguintes destinos: <a name="call-routing-options" ></a>

- **Pessoa na organização** -uma pessoa em sua organização que pode receber chamadas de voz. Pode ser um usuário online ou um usuário hospedado no local usando o Skype for Business Server.
- **Aplicativo de voz** -outro atendedor automático ou uma fila de chamadas. (Escolha a conta de recurso associada ao atendedor automático ou à fila de chamadas ao escolher este destino.)
- **Número de telefone externo** – qualquer número de telefone. (Veja [detalhes técnicos da transferência externa](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)).
- Correio **de voz-a** caixa de correio de voz associada a um grupo do Microsoft 365 que você especificar.
- **Operator** – o operador definido para o atendedor automático. A definição de um operador é opcional. O operador pode ser definido como qualquer um dos outros destinos nesta lista.

Você será solicitado a escolher uma dessas opções em diversos estágios à medida que configurar um atendedor automático.

Para configurar um atendedor automático, no centro de administração do Teams, expanda **voz** , clique em **atendedores automáticos** e, em seguida, clique em **Adicionar**.

## <a name="general-info"></a>Informações gerais

![Captura de tela das configurações do atendedor automático para nome, operador, fuso horário, idioma e entradas de voz](media/auto-attendant-general-info-page-new.png)

1. Digite um nome para o atendedor automático na caixa na parte superior.

2. Se você quiser designar um operador, especifique o destino para as chamadas para o operador. Isso é opcional (mas recomendado). Você pode definir a opção de **operador** para permitir que os chamadores quebrem nos menus e falar com uma pessoa designada.

3. Especifique o fuso horário para este atendedor automático. O fuso horário é usado para calcular o horário comercial se você [criar um fluxo de chamadas separado para o expediente](#call-flow-for-after-hours).

4. Especifique um idioma para este atendedor automático. Esse é o idioma que será usado para solicitações de voz geradas pelo sistema.

5. Escolha se deseja habilitar as entradas de voz. Quando habilitado, o nome de cada opção de menu se torna uma palavra-chave de reconhecimento de fala. Por exemplo, os chamadores podem dizer "um" para selecionar a opção de menu mapeada para a tecla 1 ou podem dizer "vendas" para selecionar a opção de menu chamada "vendas".

6. Click **Next**.

## <a name="call-flow"></a>Fluxo de chamadas

![Captura de tela das configurações da mensagem de saudação](media/auto-attendant-call-flow-greeting-message.png)

Escolha se deseja reproduzir uma saudação quando o atendedor automático atender a uma chamada.

Se você selecionar **executar um arquivo de áudio** , poderá usar o botão **carregar arquivo** para carregar uma mensagem de saudação gravada salva como áudio. WAV,. MP3 ou. Formato WMA. A gravação não pode ter mais de 5 MB.

Se você selecionar **digitar uma mensagem de saudação** , o sistema lerá o texto que você digitar (até 1000 caracteres) quando o atendedor automático atender a uma chamada.

![Captura de tela das configurações de roteamento de chamadas](media/auto-attendant-call-flow-route-call-message.png)

Escolha como você deseja direcionar a chamada.

Se você selecionar **Desconectar** , o atendedor automático irá desligar a chamada.

Se você selecionar **redirecionar chamada** , poderá escolher um dos destinos de roteamento de chamadas.

Se você selecionar **Opções do menu reproduzir** , poderá optar por **reproduzir um arquivo de áudio** ou **digitar uma mensagem de saudação** e escolher entre as opções do menu e a pesquisa de diretório.

### <a name="menu-options"></a>Opções do menu

![Captura de tela das opções da tecla de discagem](media/auto-attendant-call-flow-menu-options-complete.png)

Para opções de discagem, você pode atribuir as chaves 0-9 no teclado de telefone a um dos destinos de roteamento de chamadas. (As teclas \* (Repetir) e \# (verso) são reservados pelo sistema e não podem ser reatribuídos.)

Os mapeamentos de chave não precisam ser contínuos. É possível, por exemplo, criar um menu com as teclas 0, 1 e 3 mapeadas para as opções, enquanto que a 2 chave não seja usada.

Recomendamos mapear a chave 0 para a operadora se você tiver configurado uma. Se o operador não estiver definido como qualquer chave, o comando de voz "operador" também será desabilitado. 

Para cada opção de menu, especifique o seguinte:

- **Tecla de discagem** -a tecla no teclado do telefone para acessar esta opção. Se as entradas de voz estiverem disponíveis, os chamadores também poderão dizer esse número para acessar a opção.

- **Comando de voz** -define o comando de voz que um chamador pode conceder para acessar essa opção, se as entradas de voz estiverem habilitadas. Ele pode conter várias palavras como "atendimento ao cliente" ou "operações e aterramento". Por exemplo, o chamador pode pressionar 2, dizer "dois", ou dizer "vendas" para selecionar a opção mapeada para a chave 2. Esse texto também é renderizado por texto em fala para o prompt de confirmação do serviço, que pode ser algo parecido com "Transferindo sua chamada para vendas".

- **Redirecionar para** -o destino de roteamento de chamadas usado quando os chamadores escolhem essa opção. Se você estiver redirecionando para um atendedor automático ou fila de chamadas, escolha a conta do recurso associada a ele.

### <a name="directory-search"></a>Pesquisa de diretório

Se você atribuir chaves de discagem aos destinos, recomendamos que você escolha **nenhuma** para **pesquisa de diretório**. Se um usuário tentar discar um nome ou uma extensão usando chaves atribuídas a destinos específicos, eles podem ser roteados inesperadamente para um destino antes de terminarem de digitar o nome ou a extensão. Recomendamos que você crie um atendedor automático separado para a pesquisa de diretório e tenha o link principal do atendedor automático por meio de uma tecla de discagem.

Se você não atribuiu teclas de discagem, selecione uma opção para **pesquisa de diretório**.

**Discar por nome** -se você habilitar essa opção, os chamadores poderão dizer o nome do usuário ou digitá-lo no teclado do telefone. Qualquer usuário online com uma licença de sistema telefônico ou qualquer usuário hospedado no local usando o Skype for Business Server é um usuário elegível e pode ser encontrado com o nome discado. (Você pode definir quem é e não está incluído no diretório na página de [escopo de discagem](#dial-scope) ).

**Discar por extensão** -se você habilitar essa opção, os chamadores poderão se conectar aos usuários na sua organização discando a extensão do telefone. Qualquer usuário online com uma licença do sistema telefônico ou qualquer usuário hospedado no local usando o Skype for Business Server é um usuário elegível e pode ser encontrado com a **extensão dial** -to. (Você pode definir quem é e não está incluído no diretório na página de [escopo de discagem](#dial-scope) ).

Os usuários que você deseja disponibilizar por ramal devem ter uma extensão especificada como parte de um dos seguintes atributos de telefone definidos no Active Directory ou Active Directory do Azure (consulte [Adicionar usuários individualmente ou em massa](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) para obter mais informações.)

- OfficePhone
- HomePhone
- Celular/MobilePhone
- TelephoneNumber/intervalo
- OtherTelephone

O formato obrigatório para inserir a extensão no campo de número de telefone do usuário é *+ <phone number> <extension> ext* . ou *+ <phone number> x <extension>*.

Você pode definir a extensão no [centro de administração do Microsoft 365](https://admin.microsoft.com/) ou no [centro de administração do Azure Active Directory](https://aad.portal.azure.com). Pode levar até 12 horas antes que as alterações sejam disponibilizadas para atendedores automáticos e filas de chamadas.

> [!NOTE]
> Se você quiser usar os recursos **discar por nome** e **discar pelos** recursos de extensão, poderá atribuir uma tecla de discagem em seu atendedor principal para acessar um atendedor automático habilitado para **discar por nome**. Nesse atendedor automático, você pode atribuir uma tecla 1 (que não tem letras associadas a ela) para alcançar o atendedor automático de **discagem por extensão** .

Depois de selecionar uma opção de **pesquisa de diretório** , clique em **Avançar**.

## <a name="call-flow-for-after-hours"></a>Fluxo de chamadas por horas extras

![Captura de tela das configurações de horas e dia da hora](media/auto-attendant-business-hours.png)

O horário comercial pode ser definido para cada atendedor automático. Se os horários comerciais não forem definidos, todos os dias e todas as horas do dia serão considerados horários comerciais, porque um cronograma 24/7 é definido por padrão. O horário comercial pode ser definido com quebras de horário durante o dia, e todas as horas que não estão definidas como horário comercial são consideradas após o expediente. Você pode definir diferentes opções de atendimento de chamadas e saudações por horas extras.

Dependendo de como você configurou seus atendedores automáticos e filas de chamadas, talvez você só precise especificar o roteamento de chamadas após a hora para atendedores automáticos com números de telefone diretos.

Se você quiser um encaminhamento de chamadas separado para chamadores após a hora e, em seguida, especifique o horário comercial para cada dia. Clique em **Adicionar novo horário** para especificar vários conjuntos de horas para um determinado dia, por exemplo, para especificar um intervalo de almoço.

Depois de especificar o horário comercial, escolha as opções de roteamento de chamadas para o expediente. As mesmas opções estão disponíveis para o encaminhamento de chamadas do horário comercial que você especificou acima.

Clique em **Avançar** quando terminar.

## <a name="call-flows-during-holidays"></a>Fluxos de chamadas durante feriados

![Captura de tela das configurações de saudação de feriado e feriado](media/auto-attendant-holiday-greeting.png)

O atendedor automático pode ter um fluxo de chamadas para cada [feriado que você configurou](set-up-holidays-in-teams.md). Você pode adicionar até 20 feriados agendados para cada atendedor automático.

1. Na página de configurações de chamadas de Natal, clique em **Adicionar**.

2. Digite um nome para esta configuração de feriado.

3. Na lista suspensa **feriado** , escolha o feriado que você deseja usar.

4. Escolha o tipo de saudação que você deseja usar.

    ![Captura de tela das configurações de ação das chamadas de Natal](media/auto-attendant-holiday-actions.png)

5. Escolha se deseja **Desconectar** ou **redirecionar** a chamada.

6. Se você optou por redirecionar, escolha o destino de roteamento de chamadas para a chamada.

7. Clique em **Salvar**.

![Captura de tela das configurações de feriado com feriados listados](media/auto-attendant-holiday-call-settings.png)

Repita o procedimento conforme necessário para cada feriado adicional.

Depois de adicionar todos os seus feriados, clique em **Avançar**.

## <a name="dial-scope"></a>Escopo de discagem

![Captura de tela das opções incluir e excluir do escopo de discagem](media/auto-attendant-dial-scope.png)

O *escopo de discagem* define quais usuários estão disponíveis no diretório quando um chamador usa discar por nome ou discagem por extensão. O padrão de **todos os usuários online** inclui todos os usuários em sua organização que são usuários online com uma licença do sistema telefônico ou hospedada no local usando o Skype for Business Server.

Você pode incluir ou excluir usuários específicos selecionando **grupo de usuários personalizado** em **incluir** ou **excluir** e escolhendo um ou mais grupos do Microsoft 365, listas de distribuição ou grupos de segurança. Por exemplo, talvez você queira excluir executivos de sua organização do diretório de discagem. (Se um usuário estiver em ambas as listas, eles serão excluídos do diretório.)

> [!NOTE]
> Pode levar até 36 horas para que um novo usuário tenha o nome listado no diretório.

Quando terminar de configurar o escopo de discagem, clique em **Avançar**.

## <a name="resource-accounts"></a>Contas de recursos

Todos os atendedores automáticos devem ter uma conta de recurso associada.  Os atendedores automáticos de primeiro nível precisarão pelo menos uma conta de recurso que tenha um número de serviço associado. Se quiser, você pode atribuir várias contas de recurso a um atendedor automático, cada uma com um número de serviço separado.

![Captura de tela da conta do recurso Adicionar painel de contas](media/auto-attendant-add-resource-account.png)

Para adicionar uma conta de recurso, clique em **adicionar conta** e procure a conta que você deseja adicionar. Clique em **Adicionar** e, em seguida, clique em **Adicionar**.

![Captura de tela da lista conta de recurso mostrando a conta do recurso com número de serviço atribuído](media/auto-attendant-resource-account-assigned.png)

Quando terminar de adicionar contas de serviço, clique em **Enviar**. Isso conclui a configuração do atendedor automático.

## <a name="external-phone-number-transfers---technical-details"></a>Transferências de número de telefone externo-detalhes técnicos

Ao transferir chamadas para um número de telefone externo, a conta de recurso associada ao atendedor automático ou à fila de chamadas deve ter um número de telefone e um sistema telefônico Microsoft 365-licença de usuário virtual. Além

- Para uma conta de recurso com um número de plano de chamada, atribua uma licença de [plano de chamada](calling-plans-for-office-365.md) .
  - O número de telefone de transferência externa deve ser inserido no formato E. 164 (+ CC + phone_number).

- Para uma conta de recurso com um número de roteamento direto, atribua uma [política de roteamento de voz online](manage-voice-routing-policies.md).
  - O formato de número de telefone de transferência externa depende de suas configurações de [SBC (controlador de borda de sessão)](https://docs.microsoft.com/microsoftteams/direct-routing-connect-the-sbc) .

O número de telefone de saída exibido é determinado da seguinte maneira:

  - Para números de plano de chamada, o número de telefone do chamador original é exibido.
  - Para números de roteamento direto, o número enviado é baseado na configuração P-Assertd-Identity (PAI) no SBC, da seguinte maneira:
    - Se definido como Disabled, o número de telefone do chamador original será exibido. Esta é a configuração padrão e recomendada.
    - Se definido como habilitado, o número de telefone da conta do recurso será exibido.

Não há suporte para transferências entre troncos de plano de chamada e troncos diretos de roteamento.

Em um ambiente híbrido do Skype for Business, para transferir uma chamada de atendedor automático para a PSTN, crie um novo usuário local com encaminhamento de chamadas definido para o número PSTN. O usuário deve estar habilitado para o Enterprise Voice e ter uma política de voz atribuída. Para saber mais, consulte [transferência de chamadas de atendedor automático para PSTN](https://docs.microsoft.com/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn).

### <a name="create-an-auto-attendant-with-powershell"></a>Criar um atendedor automático com o PowerShell

Você também pode usar o PowerShell para criar e configurar atendedores automáticos. Estes são os cmdlets necessários para gerenciar um atendedor automático:

- [New-CsAutoAttendant](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant)  
- [Set-CsAutoAttendant](https://docs.microsoft.com/powershell/module/skype/set-csautoattendant)
- [Get-CsAutoAttendant](https://docs.microsoft.com/powershell/module/skype/get-csautoattendant)
- [Get-CsAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/get-csautoattendantholidays)
- [Remove-CsAutoAttendant](https://docs.microsoft.com/powershell/module/skype/remove-csautoattendant)
- [New-CsAutoAttendantMenu](https://docs.microsoft.com/powershell/module/skype/new-csautoattendantmenu)
- [New-CsOnlineAudioFile](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineAudioFile)
- [New-CsAutoAttendantCallFlow](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallFlow)
- [Export-CsAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/export-csorganizationalautoattendantholidays)
- [New-CsOnlineTimeRange](https://docs.microsoft.com/powershell/module/skype/new-csonlinetimerange)
- [New-CsOnlineDateTimeRange](https://docs.microsoft.com/powershell/module/skype/new-csonlinedatetimerange)
- [New-CsOnlineSchedule](https://docs.microsoft.com/powershell/module/skype/New-CsOnlineSchedule)
- [Get-CsAutoAttendantSupportedTimeZone](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone)
- [New-CsAutoAttendantCallHandlingAssociation](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation)
- [Get-CsAutoAttendantSupportedLanguage](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage)
- [Import-CsAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/import-csautoattendantholidays)
- [New-CsAutoAttendantCallableEntity](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallableEntity)


## <a name="related-topics"></a>Tópicos relacionados

[Veja o que você obtém com o Sistema de Telefonia](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[Obter números de telefone de serviço](/microsoftteams/getting-service-phone-numbers)

[Disponibilidade de audioconferência e Planos de Chamadas por país e região](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

[Exemplo de pequena empresa – configurar um atendedor automático](/microsoftteams/tutorial-org-aa) 

[Uma introdução ao Windows PowerShell e ao Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
