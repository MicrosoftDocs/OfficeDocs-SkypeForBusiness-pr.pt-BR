---
title: Configurar um atendedor automático para o Microsoft Teams
author: DaniEASmith
ms.author: danismith
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
ms.custom:
- Phone System
description: Saiba como configurar e gerenciar atendedores automáticos no Microsoft Teams.
ms.openlocfilehash: 18ff00dc72a69ea5aed85a3531a100e28f2891d1
ms.sourcegitcommit: 507e186972bcbc56c1547a1b9f357bfd38170b5a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2022
ms.locfileid: "68046681"
---
# <a name="set-up-an-auto-attendant"></a>Configurar um atendedor automático

Os atendedores automáticos permitem que as pessoas liguem para sua organização e naveguem por um sistema de menus para falar com o departamento certo, fila de chamadas, pessoa ou operador. Você pode criar atendedores automáticos para sua organização com o centro de administração do Microsoft Teams ou com o PowerShell.

Verifique se você leu o [Plano para atendedores automáticos do Teams e as filas](plan-auto-attendant-call-queue.md) de [](plan-auto-attendant-call-queue.md#getting-started) chamadas e seguiu as etapas de introdução antes de seguir os procedimentos neste artigo.

Os atendedores automáticos podem redirecionar chamadas, com base na entrada dos chamadores, para um dos seguintes destinos:

- **Operador** – o operador definido para o atendedor automático. Definir um operador é opcional. O operador pode ser definido como qualquer um dos outros destinos nesta lista.
- **Pessoa na organização –** uma pessoa em sua organização que pode receber chamadas de voz. Essa pessoa pode ser um usuário online ou um usuário hospedado localmente usando Skype for Business Server.
- **Aplicativo de voz** – outro atendedor automático ou uma fila de chamadas. (Escolha a conta de recurso associada ao atendedor automático ou fila de chamadas ao escolher esse destino.)
- **Caixa** postal – a caixa de correio de voz associada a um grupo do Microsoft 365 especificado por você. Você pode escolher se deseja transcrições de caixa postal e "Deixe uma mensagem após o tom". prompt do sistema.
  - No M365 Administração Center, habilite "Permitir que pessoas de fora da organização enviem email para esta equipe" para o grupo do Microsoft 365 especificado
- **Número de telefone externo** - qualquer número de telefone. Consulte [detalhes técnicos de transferência externa](create-a-phone-system-auto-attendant.md?tabs=general-info#external-phone-number-transfers---technical-details).
- **Comunicado (arquivo de áudio)** – Reproduzir um arquivo de áudio. Uma mensagem de anúncio gravada que você carrega salva como áudio em . WAV, .MP3 ou . Formato WMA. A gravação não pode ser maior que 5 MB. O sistema reproduz o comunicado e, em seguida, retorna ao menu atendedor automático.
- **Comunicado (Digitado)** – digite uma mensagem. Texto que você deseja que o sistema leia. Você pode inserir até 1000 caracteres. O sistema reproduz o comunicado e, em seguida, retorna ao menu atendedor automático.

> [!NOTE]
> Ao redirecionar chamadas para **uma Pessoa na organização**, essa pessoa deve estar habilitada para voz. Para obter detalhes sobre como habilitar a voz, [consulte Atribuir licenças de complemento do Teams aos usuários](teams-add-on-licensing/assign-teams-add-on-licenses.md).
>
> Embora a definição **de um operador** seja opcional, é recomendável.  Os atendedores automáticos redirecionam chamadas para o operador se o chamador não fizer uma seleção em menus, selecionar repetidamente opções inválidas ou discar por nome ou número falhar repetidamente.  Se um operador não estiver definido, o atendedor automático descartará a chamada.

## <a name="whats-new-for-auto-attendants-in-the-past-6-months"></a>Novidades para atendedores automáticos nos últimos 6 meses
 
 - Setembro – **A opção Forçar Escuta** agora está disponível com a opção **de menu** Reproduzir para o fluxo de chamadas, o fluxo de chamadas para horas extras e o fluxo de chamadas durante feriados.
 - Agosto – **As opções do menu** Reproduzir no fluxo de chamadas, no fluxo de chamadas para horas extras e no fluxo de chamadas durante feriados \* agora dão suporte a chaves (asterisco) \# e (libra).
 - Julho – O fluxo de chamadas durante feriados agora dá suporte **a opções de menu Reproduzir**.
 
## <a name="steps-to-create-an-auto-attendant"></a>Etapas para criar um atendedor automático
As etapas para adicionar um atendedor automático são:

1. Configurar informações gerais.
1. Configurar um fluxo de chamada básico.
1. Configure um fluxo de chamadas após o horário comercial.
1. Configurar fluxos de chamadas de feriados.
1. Configurar o escopo de discagem.
1. Configurar contas de recursos.

As etapas descritas no artigo criam atendedores automáticos usando o centro de administração do Teams. Para obter instruções **para criar atendedores automáticos usando o PowerShell**, consulte [Criando atendedores automáticos com cmdlets do PowerShell](create-a-phone-system-auto-attendant-via-cmdlets.md).

## <a name="follow-these-steps-to-set-up-your-auto-attendant"></a>Siga estas etapas para configurar o atendedor automático

# <a name="step-1-general-info"></a>[Etapa 1: Informações gerais](#tab/general-info)

## <a name="step-1-set-the-auto-attendants-general-information"></a>Etapa 1: Definir as informações gerais do atendedor automático

Para configurar um atendedor automático, no centro de administração do [Teams](https://go.microsoft.com/fwlink/p/?linkid=2066851)**, expanda** Voz, selecione **Atendedores automáticos** e, em seguida, **selecione Adicionar**.

1. Digite um nome para o atendedor automático na caixa na parte superior.

2. Para designar um operador, especifique o destino para chamadas ao operador. Essa designação é opcional, mas recomendada. Defina **a opção** Operador para permitir que os chamadores interrompam os menus e conversem com uma pessoa designada.

3. Especifique o fuso horário para esse atendedor automático. O fuso horário será usado para calcular o horário comercial se você [criar um fluxo de chamada separado para horas extras](?tabs=after-hours).

4. [Especifique um idioma com suporte](create-a-phone-system-auto-attendant-languages.md) para esse atendedor automático. Esse é o idioma que será usado para prompts de voz gerados pelo sistema.

5. Escolha se deseja habilitar entradas de voz. Quando habilitado, o nome de cada opção de menu se torna uma palavra-chave de reconhecimento de fala. Por exemplo, os chamadores podem dizer "Um" para selecionar a opção de menu mapeada para a tecla 1 ou podem dizer "Vendas" para selecionar a opção de menu chamada "Vendas".

   > [!NOTE]
   > Se você escolher um idioma na Etapa 4 que não dá suporte a entradas de voz, essa opção será desabilitada.

Depois de definir as informações gerais do atendedor automático, selecione **Avançar**.

# <a name="step-2-basic-call-flow"></a>[Etapa 2: Fluxo de chamadas básico](#tab/call-flow)

## <a name="step-2-set-up-the-basic-call-flow"></a>Etapa 2: Configurar o fluxo de chamada básico

### <a name="set-a-greeting"></a>Definir uma saudação

- Se você selecionar **Reproduzir um arquivo de áudio** , poderá usar o **botão** Carregar arquivo para carregar uma mensagem de saudação gravada salva como áudio em . WAV, .MP3 ou . Formato WMA. A gravação não pode ser maior que 5 MB.

- Se você selecionar **Digitar uma mensagem** de saudação, o sistema lerá o texto que você digitar (até 1000 caracteres) quando o atendedor automático atender uma chamada.

### <a name="route-the-call"></a>Rotear a chamada

- Se você selecionar **Desconectar**, o atendedor automático desligará a chamada.
- Se você selecionar **Redirecionar chamada**, poderá escolher um dos destinos de roteamento de chamadas.
- Se você selecionar **opções de menu** Reproduzir, poderá optar por  Reproduzir um arquivo de áudio ou Digitar uma mensagem de saudação e, em seguida, escolher entre as opções de menu e **a** pesquisa de diretório.

#### <a name="play-menu-options"></a>Opções do menu Reproduzir

*Nova – a opção Forçar escuta pode ser habilitada, o que exige que os chamadores ouçam todas as opções de menu antes de fazer a seleção.*
 *As teclas New - \* (asterisco) \# e (pound) agora podem ser usadas nas opções de menu*.

Para opções de discagem, atribua as teclas de 0 a 9 no teclado telefônico a um dos destinos de roteamento de chamadas. As chaves \* (asterisco) \# e (libra) são reservadas pelo sistema e não podem ser reatribuídas. Pressionar uma dessas teclas repetirá o menu atual.

> [!NOTE]
> A tecla #só faz backup para o atendedor automático mais recente. Depois que o limite for cruzado para um novo atendedor automático, a tecla # não poderá levá-lo até o anterior.

Mapeamentos de chave não precisam ser contínuos. É possível criar um menu com as teclas 0, 1 e 3 mapeadas para opções, enquanto a tecla número 2 não é usada.

Recomendamos mapear a chave zero para o operador se você tiver configurado uma. Se o operador não estiver definido como nenhuma chave, o comando de voz "Operador" também será desabilitado.

Para cada opção de menu, especifique as seguintes configurações:

- **Tecla de** discagem – a chave no teclado do telefone para acessar essa opção. Se houver entradas de voz disponíveis, os chamadores também poderão dizer esse número para acessar a opção.

- **Comando de** voz – define o comando de voz que um chamador pode dar para acessar essa opção, se as entradas de voz estão habilitadas. Ele pode conter várias palavras, como "Atendimento ao Cliente" ou "Operações e Motivos". Por exemplo, o chamador pode pressionar 2, dizer "dois" ou dizer "Vendas" para selecionar a opção mapeada para as duas teclas. Esse texto também é renderizado por conversão de texto em fala para o prompt de confirmação do serviço, que pode ser algo como "Transferindo sua chamada para vendas".

- **Redirecionar para** – o destino de roteamento de chamadas usado quando os chamadores escolhem essa opção. Se você estiver redirecionando para um atendedor automático ou fila de chamadas, escolha a conta de recurso associada a ela.

##### <a name="directory-search"></a>Pesquisa de diretório

Se você atribuir chaves de discagem a destinos, recomendamos que você escolha **Nenhuma** para **pesquisa de diretório**. Se um chamador tentar discar um nome ou extensão usando chaves atribuídas a destinos específicos, ele poderá ser roteado inesperadamente para um destino antes de terminar de inserir o nome ou a extensão. Recomendamos que você crie um atendedor automático separado para pesquisa de diretório e tenha o link principal do atendedor automático com uma chave de discagem.

Se você não atribuiu chaves de discagem, escolha uma opção para pesquisa **de diretório**.

**Discar por nome** – Se você habilitar essa opção, os chamadores poderão dizer o nome do usuário ou digitá-lo no teclado do telefone. Qualquer usuário online ou qualquer usuário hospedado localmente usando o Skype for Business Server, é um usuário qualificado e pode ser encontrado com o Dial por nome.

**Discar por extensão** – se você habilitar essa opção, os chamadores poderão se conectar com os usuários em sua organização discando sua extensão de telefone. Qualquer usuário online ou qualquer usuário hospedado localmente usando o Skype for Business Server, é um usuário qualificado e pode ser encontrado com **o Dial por extensão**. (Você pode definir quem é e não está incluído no diretório na página de escopo [do Dial](?tabs=dial-scope) .)

> [!NOTE]
> Se você quiser usar os recursos Discar por nome e  Discar por extensão, poderá atribuir uma tecla de discagem no atendedor automático principal para acessar um atendedor automático habilitado para Discar **por nome**. Dentro desse atendedor automático, você pode atribuir a tecla 1 (que não tem letras associadas a ela) para alcançar o atendedor automático **de** discagem por extensão.

Para obter mais informações, consulte o [Dial e a referência de voz](dial-voice-reference.md).

Depois de definir as opções básicas de fluxo de chamadas, selecione **Avançar**.

# <a name="step-3-after-hours-call-flow"></a>[Etapa 3: Fluxo de chamadas após o horário comercial](#tab/after-hours)

## <a name="step-3-set-up-call-flow-for-after-hours-optional"></a>Etapa 3: Configurar o fluxo de chamadas para horas extras (opcional)

O horário comercial pode ser definido para cada atendedor automático.

- Se os horários comerciais não forem definidos, todos os dias e todas as horas do dia serão considerados horários comerciais, porque um cronograma 24/7 é definido por padrão.
- O horário comercial pode ser definido com intervalos no tempo durante o dia e todas as horas que não estão definidas como horas comerciais são consideradas após o horário comercial.
- Você pode definir diferentes opções de tratamento de chamadas de entrada e saudações para o horário de expediente.

Dependendo de como você configurou seus atendedores automáticos e filas de chamadas, talvez seja necessário especificar apenas o roteamento de chamadas após o horário comercial para atendedores automáticos com números de telefone diretos.

Se você quiser roteamento de chamadas separado para chamadores após o horário comercial, especifique seu horário comercial para cada dia.

1. Ao lado do dia da semana na tabela, ajuste a tela **Inicial em** e **Fim às** vezes.
1. Se necessário, selecione **Adicionar novo horário** para especificar vários conjuntos de horas para um determinado dia, por exemplo, para especificar uma pausa de almoço.
1. Escolha as opções de roteamento de chamadas para horas extras. As mesmas opções gerais de fluxo de chamadas também estão disponíveis para horas extras.

Depois de adicionar o fluxo de chamadas após o horário comercial, selecione **Avançar**.

# <a name="step-4-holiday-call-flow"></a>[Etapa 4: Fluxo de chamada de feriado](#tab/holidays)

## <a name="step-4-set-up-call-flows-for-holidays-optional"></a>Etapa 4: Configurar fluxos de chamada para feriados (opcional)

O atendedor automático pode ter um fluxo de chamada para cada [Feriado que você configurou](set-up-holidays-in-teams.md). Você pode adicionar até 20 feriados agendados para cada atendedor automático.

*Nova – a opção Forçar escuta pode ser habilitada, o que exige que os chamadores ouçam todas as opções de menu antes de fazer a seleção.*
 *As teclas New - \* (asterisco) \# e (pound) agora podem ser usadas nas opções de menu.*
 *Novo – **As opções do menu Reproduzir** agora estão disponíveis em fluxos de chamadas de feriados.*

1. Na página configurações de chamada de Feriado, selecione **Adicionar**.

1. Digite um nome para essa configuração de feriado.

1. Na lista **suspensa Feriado** , escolha o feriado que você deseja usar.

1. Escolha o tipo de saudação que você deseja usar.

1. Escolha se deseja **desconectar** ou **redirecionar** a chamada.

    1. Se você optar por redirecionar, escolha o destino de roteamento de chamadas para a chamada.
    1. Se você optar por reproduzir opções de menu, configure as **opções do menu Reproduzir**.

1. Selecione **Salvar**.

Repita o procedimento conforme necessário para cada feriado adicional.

Depois de adicionar todas as suas horas de feriado, selecione **Avançar**.

# <a name="step-5-dial-scope"></a>[Etapa 5: Escopo de discagem](#tab/dial-scope)

## <a name="step-5-set-up-dial-scope-optional"></a>Etapa 5: Configurar o escopo de discagem (opcional)

O *escopo de* discagem define quais usuários estão disponíveis no diretório quando um chamador usa discagem por nome ou discagem por extensão. O padrão de **Todos os usuários online** inclui todos os usuários em sua organização que são usuários online ou hospedados localmente usando Skype for Business Server.

Você pode incluir ou excluir usuários específicos selecionando Grupo de usuários  personalizado em  Incluir ou Excluir e escolhendo um ou mais grupos do Microsoft 365, listas de distribuição ou grupos de segurança. Por exemplo, talvez você queira excluir executivos em sua organização do diretório de discagem.

Se um usuário estiver em ambas as listas, ele será excluído do diretório.

> [!NOTE]
> Pode levar até 36 horas para que um novo usuário tenha seu nome listado no diretório.

Depois de selecionar as opções de escopo **do Dial** , selecione **Avançar**.

# <a name="step-6-resource-accounts"></a>[Etapa 6: Contas de recursos](#tab/resource-accounts)

## <a name="step-6-set-up-resource-accounts-optional"></a>Etapa 6: Configurar contas de recursos (opcional)

Todos os atendedores automáticos devem ter uma conta de recurso associada.  Os atendedores automáticos de primeiro nível precisarão de pelo menos uma conta de recurso que tenha um número de serviço associado. Se desejar, você pode atribuir várias contas de recurso a um atendedor automático, cada uma com um número de serviço separado.

Para adicionar uma conta de recurso, **selecione Adicionar conta** e pesquise a conta que você deseja adicionar. Selecione **Adicionar** e, em seguida, **selecione Adicionar**.

Depois de adicionar contas de recursos, selecione **Avançar**.

Consulte [Gerenciar contas de recursos do Teams](manage-resource-accounts.md) para obter mais informações.

---

## <a name="resources-for-complex-scenarios"></a>Recursos para cenários complexos

### <a name="external-phone-number-transfers---technical-details"></a>Transferências de número de telefone externo – detalhes técnicos

Consulte os [Pré-requisitos para](plan-auto-attendant-call-queue.md#prerequisites) permitir que os atendedores automáticos transfira chamadas externamente.  Além disso:

- Para uma conta de recurso com [](calling-plans-for-office-365.md) uma licença de Plano [](operator-connect-plan.md) de Chamada ou um número de Conexão do Operador, o número de telefone de transferência externa deve ser inserido no formato E.164 (+[código do país][código de área][número de telefone]).

- Para uma conta de recurso com uma política de roteamento de voz online de Licença Telefonia do Microsoft Teams e Roteamento Direto, o formato de número de telefone de transferência externa depende das configurações do Controlador de Borda de Sessão [(SBC](direct-routing-connect-the-sbc.md)).

O número de telefone de saída exibido é determinado da seguinte maneira:

- Para números de Plano de Chamada e Conexão do Operador, o número de telefone do chamador original é exibido.
- Para números de Roteamento Direto, o número enviado baseia-se na configuração de PAI (identidade P-Asserted-Identity) no SBC, da seguinte maneira:
  - Se definido como Desabilitado, o número de telefone do chamador original será exibido. Essa é a configuração padrão e recomendada.
  - Se definido como Habilitado, o número de telefone da conta de recurso será exibido.

Em um Skype for Business híbrido, para transferir uma chamada de atendedor automático para o PSTN, crie um novo usuário local com o encaminhamento de chamadas definido como o número PSTN. O usuário deve estar habilitado para Enterprise Voice e ter uma política de voz atribuída. Para saber mais, confira [Transferência de chamada de atendedor automático para PSTN](/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn).

### <a name="auto-attendant-diagnostic-tool"></a>Ferramenta de Diagnóstico do Atendedor Automático

Se você for um administrador, poderá usar a seguinte ferramenta de diagnóstico para validar se um atendedor automático é capaz de receber chamadas:

1. Selecione **Executar testes** abaixo, o que preencherá o diagnóstico no Centro de Administração do Microsoft 365.

   > [!div class="nextstepaction"]
   > [Executar testes: Atendedor Automático do Teams](https://aka.ms/TeamsAADiag)

2. No painel Executar diagnóstico, insira a Conta de Recurso no nome de usuário **ou** Email e selecione **Executar Testes**.

3. Os testes identificarão configurações de locatário, política ou conta de recurso que estão impedindo o atendedor automático de receber chamadas e fornecerão etapas para corrigir quaisquer problemas identificados.

### <a name="related-topics"></a>Tópicos relacionados

[Veja o que você obtém com o Telefone do Teams](./here-s-what-you-get-with-phone-system.md)

[Obter números de telefone de serviço](./getting-service-phone-numbers.md)

[Disponibilidade de Audioconferência e Planos de Chamadas por país e região](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[Uma introdução ao Windows PowerShell e ao Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
