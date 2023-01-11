---
title: Configurar um assistente automático do Microsoft Teams
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
- highpri
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
ms.custom:
- Phone System
adobe-target: true
adobe-target-activity: DocsExp–480823–A/B–Docs/TeamsSteps–HowToTabs–FY22Q2
adobe-target-experience: Experience B
adobe-target-content: ./create-a-phone-system-auto-attendant-experiment
description: Saiba como configurar e gerenciar atendentes automáticos no Microsoft Teams.
ms.openlocfilehash: 11fcf4016cd6ef8f2f4301c18c9362af6bed30ec
ms.sourcegitcommit: ae687f530d5505b96df7cb7ef4da3a36bd9afd29
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/10/2023
ms.locfileid: "69763542"
---
# <a name="set-up-a-microsoft-teams-auto-attendant"></a>Configurar um assistente automático do Microsoft Teams

Os atendentes automáticos permitem que as pessoas chamem sua organização e naveguem por um sistema de menus para falar com o departamento certo, chamar fila, pessoa ou um operador. Você pode criar atendentes automáticos para sua organização com o centro de administração do Microsoft Teams ou com o PowerShell.

Certifique-se de ter lido [Plano para atendentes automáticos do Teams e filas de chamadas](plan-auto-attendant-call-queue.md) e seguido as [etapas de introdução](plan-auto-attendant-call-queue.md#getting-started) antes de seguir os procedimentos neste artigo.

Os atendentes automáticos podem redirecionar chamadas, com base na entrada dos chamadores, para um dos seguintes destinos:

- **Operador** – o operador definido para o atendente automático. Definir um operador é opcional. O operador pode ser definido como qualquer um dos outros destinos desta lista.
- **Pessoa na organização** – uma pessoa em sua organização que pode receber chamadas de voz. Essa pessoa pode ser um usuário online ou um usuário hospedado localmente usando Skype for Business Server.
- **Aplicativo de voz** – outro atendente automático ou uma fila de chamadas. Escolha a conta de recurso associada ao atendente automático ou à fila de chamadas ao escolher esse destino.
- **Caixa postal** – a caixa de correio de voz associada a um grupo do Microsoft 365 que você especifica. Você pode escolher se deseja transcrições de caixa postal e "Por favor, deixe uma mensagem após o tom". prompt do sistema.
  - Em Centro de administração do Microsoft 365, habilite **Permitir que pessoas fora da organização enviem este email para essa equipe** para o grupo do Microsoft 365 que você especificar.
- **Número de telefone externo** – qualquer número de telefone. Confira [detalhes técnicos de transferência externa](create-a-phone-system-auto-attendant.md?tabs=general-info#external-phone-number-transfers---technical-details).
- **Comunicado (arquivo de áudio)** – Reproduzir um arquivo de áudio. Uma mensagem de anúncio gravada que você carrega salva como áudio no . WAV, .MP3 ou . Formato WMA. A gravação não pode ser maior que 5 MB. O sistema reproduz o anúncio e retorna ao menu de atendimento automático.
- **Comunicado (Digitado)** – Digite uma mensagem. Texto que você deseja que o sistema leia. Você pode inserir até 1000 caracteres. O sistema reproduz o anúncio e retorna ao menu de atendimento automático.

> [!NOTE]
> Ao redirecionar chamadas para uma **pessoa na organização**, essa pessoa deve estar habilitada para voz. Para obter detalhes sobre como habilitar a voz, confira [Atribuir licenças de complemento do Teams aos usuários](teams-add-on-licensing/assign-teams-add-on-licenses.md).
>
> Embora a definição de um **Operador** seja opcional, é recomendável.  Os atendentes automáticos redirecionam chamadas para o operador se houver um erro na configuração do atendente automático devido à exclusão de uma conta de caixa postal compartilhada ou usuário.  Se um operador não estiver definido, o atendente automático cancelará a chamada.

## <a name="whats-new-for-auto-attendants-in-the-past-six-months"></a>Novidades para os atendentes automáticos nos últimos seis meses

- Setembro – A opção **Forçar Escutar** agora está disponível com **a opção De menu Reproduzir** para fluxo de chamadas, Fluxo de chamadas para depois do horário e Fluxo de chamadas durante feriados.
- Agosto – **Opções de menu reproduzir** no fluxo de chamadas, Fluxo de chamadas para depois do horário e Fluxo de chamadas durante feriados agora suportam \* chaves (asterisco) e \# (libra).

## <a name="steps-to-create-an-auto-attendant"></a>Etapas para criar um atendente automático

As etapas para adicionar um atendente automático são:

1. Configure informações gerais.
1. Configure um fluxo de chamada básico.
1. Configure um fluxo de chamadas após o expediente.
1. Configure fluxos de chamadas de feriado.
1. Configurar o escopo de discagem.
1. Configurar contas de recursos.

As etapas descritas no artigo criam atendentes automáticos usando o centro de administração do Teams. Para obter instruções para **criar atendentes automáticos usando o PowerShell**, consulte [Criando atendentes automáticos com cmdlets do PowerShell](create-a-phone-system-auto-attendant-via-cmdlets.md).

## <a name="follow-these-steps-to-set-up-your-auto-attendant"></a>Siga estas etapas para configurar o assistente automático

## <a name="step-1-general-info"></a>[Etapa 1: Informações gerais](#tab/general-info)

## <a name="step-1-set-the-auto-attendants-general-information"></a>Etapa 1: Definir as informações gerais do atendente automático

Para configurar um atendente automático, no [centro de administração do Teams](https://go.microsoft.com/fwlink/p/?linkid=2066851), expanda **Voz**, selecione **Atendentes automáticos** e selecione **Adicionar**.

1. Digite um nome para o atendente automático na caixa na parte superior.

2. Para designar um operador, especifique o destino para chamadas para o operador. Essa designação é opcional, mas recomendada. Defina a opção **Operador** para permitir que os chamadores saiam dos menus e falem com uma pessoa designada.

3. Especifique o fuso horário para este atendente automático. O fuso horário é usado para calcular o horário comercial se você [criar um fluxo de chamada separado para depois do horário](?tabs=after-hours).

4. Especifique um [idioma com suporte](create-a-phone-system-auto-attendant-languages.md) para este atendente automático. Essa linguagem será usada para prompts de voz gerados pelo sistema.

5. Escolha se deseja habilitar entradas de voz. Quando habilitado, o nome de cada opção de menu se torna uma palavra-chave de reconhecimento de fala. Por exemplo, os chamadores podem dizer "Um" para selecionar a opção de menu mapeada para a chave 1 ou podem dizer "Vendas" para selecionar a opção de menu chamada "Vendas".

   > [!NOTE]
   > Se você escolher um idioma na Etapa 4 que não dá suporte a entradas de voz, essa opção será desabilitada.

Depois de definir as informações gerais do atendente automático, selecione **Avançar**.

## <a name="step-2-basic-call-flow"></a>[Etapa 2: Fluxo de chamadas básico](#tab/call-flow)

## <a name="step-2-set-up-the-basic-call-flow"></a>Etapa 2: configurar o fluxo de chamada básico

### <a name="set-a-greeting"></a>Definir uma saudação

- Se você selecionar **Reproduzir um arquivo de áudio** , poderá usar o botão **Carregar arquivo** para carregar uma mensagem de saudação gravada salva como áudio no . WAV, .MP3 ou . Formato WMA. A gravação não pode ser maior que 5 MB.

- Se você selecionar **Digitar uma mensagem de saudação** , o sistema lerá o texto que você digitar (até 1000 caracteres) quando o atendente automático atender uma chamada.

### <a name="route-the-call"></a>Rotear a chamada

- Se você selecionar **Desconectar**, o atendente automático desligará a chamada.
- Se você selecionar **Chamada de redirecionamento**, poderá escolher um dos destinos de roteamento de chamadas.
- Se você selecionar **Opções de menu Reproduzir**, você poderá optar por **Reproduzir um arquivo de áudio** ou **Digitar uma mensagem de saudação** e, em seguida, escolher entre opções de menu e pesquisa de diretório.

#### <a name="play-menu-options"></a>Opções de menu Reproduzir

*Nova opção – A opção Forçar escuta pode ser habilitada, o que exige que os chamadores ouçam todas as opções de menu antes de fazer a seleção.*
 *Novas chaves - \* (asterisco) e \# (libra) agora podem ser usadas nas opções de menu.*

Para opções de discagem, atribua as teclas 0-9, \* (asterisco) e \# (libra) no teclado telefônico a um dos destinos de roteamento de chamada. 

Mapeamentos de chaves não precisam ser contínuos. É possível criar um menu com chaves 0, 1 e 3 mapeadas para opções, enquanto a chave número 2 não é usada.

Recomendamos mapear a chave zero para o operador se você tiver configurado uma. Se o operador não estiver definido como nenhuma chave, o comando de voz "Operador" também será desabilitado.

Para cada opção de menu, especifique as seguintes configurações:

- **Tecla discada** – a chave no teclado do telefone para acessar essa opção. Se as entradas de voz estiverem disponíveis, os chamadores também poderão dizer esse número para acessar a opção.

- **Comando de voz** – define o comando de voz que um chamador pode dar para acessar essa opção, se as entradas de voz estiverem habilitadas. Ele pode conter várias palavras como "Serviço ao Cliente" ou "Operações e Motivos". Por exemplo, o chamador pode pressionar 2, dizer "dois" ou dizer "Vendas" para selecionar a opção mapeada para as duas chaves. Este texto também é renderizado por texto para a fala para o prompt de confirmação do serviço, que pode ser algo como "Transferir sua chamada para vendas".

- **Redirecionar para** - o destino de roteamento de chamada usado quando os chamadores escolhem essa opção. Se você estiver redirecionando para um atendente automático ou fila de chamadas, escolha a conta de recurso associada a ela.

##### <a name="directory-search"></a>Pesquisa de diretório

Se você atribuir chaves de discagem a destinos, recomendamos que você escolha **Nenhuma** para **pesquisa de Diretório**. As chaves de discagem são correspondentes antes que as pesquisas de diretório sejam executadas.  Se um chamador começar a inserir um nome ou extensão usando chaves de discagem atribuídas a destinos específicos, ele será roteado para esse destino antes de terminar de inserir o nome ou a extensão. Recomendamos que você crie um assistente automático separado para pesquisa de diretório e tenha seu principal link de atendimento automático com uma chave de discagem.

Se você não atribuiu chaves de discagem, escolha uma opção para **pesquisa de Diretório**.

**Discar pelo nome** – se você habilitar essa opção, os chamadores poderão dizer o nome do usuário ou digitá-lo no teclado telefônico. Qualquer usuário online ou qualquer usuário hospedado localmente usando Skype for Business Server, é um usuário qualificado e pode ser encontrado com Discar pelo nome.

**Discar por extensão** – se você habilitar essa opção, os chamadores poderão se conectar com usuários em sua organização discando a extensão do telefone. Qualquer usuário online ou qualquer usuário hospedado localmente usando Skype for Business Server, é um usuário qualificado e pode ser encontrado com **Discar por extensão**. (Você pode definir quem é e não está incluído no diretório na página [escopo Discar](?tabs=dial-scope) .)

> [!NOTE]
> Se você quiser usar os recursos **Discar por nome** e **Discar por extensão** , poderá atribuir uma chave de discagem no atendente automático principal para alcançar um atendente automático habilitado para **Discar pelo nome**. Dentro desse atendente automático, você pode atribuir a chave 1 (que não tem letras associadas a ela) para acessar o **Assistente automático discar por extensão** .

Para obter mais informações, consulte a [referência Discar e voz](dial-voice-reference.md).

Depois de definir suas opções básicas de fluxo de chamadas, selecione **Avançar**.

## <a name="step-3-after-hours-call-flow"></a>[Etapa 3: Após o horário de fluxo de chamadas](#tab/after-hours)

## <a name="step-3-set-up-call-flow-for-after-hours-optional"></a>Etapa 3: configurar o fluxo de chamadas para depois do horário (opcional)

O horário comercial pode ser definido para cada atendente automático.

- Se os horários comerciais não forem definidos, todos os dias e todas as horas do dia serão considerados horários comerciais, porque um cronograma 24/7 é definido por padrão.
- O horário comercial pode ser definido com intervalos no tempo durante o dia e todas as horas que não são definidas como horário comercial são consideradas após o expediente.
- Você pode definir diferentes opções e saudações de tratamento de chamadas de entrada para o pós-expediente.

Dependendo de como você configurou seus atendentes automáticos e filas de chamadas, talvez seja necessário especificar o roteamento de chamadas após o expediente para atendentes automáticos com números de telefone diretos.

Se você quiser roteamento de chamadas separado para chamadores após o expediente, especifique seu horário comercial para cada dia.

1. Ao lado do dia da semana na tabela, ajuste as horas **Iniciar** e **Terminar** .
1. Se necessário, selecione **Adicionar nova hora** para especificar vários conjuntos de horas para um determinado dia, por exemplo, para especificar uma pausa para o almoço.
1. Escolha as opções de roteamento de chamadas para depois do horário. As mesmas opções gerais de fluxo de chamada também estão disponíveis para depois do horário.

Depois de adicionar o fluxo de chamadas após o expediente, selecione **Avançar**.

## <a name="step-4-holiday-call-flow"></a>[Etapa 4: Fluxo de chamadas de férias](#tab/holidays)

## <a name="step-4-set-up-call-flows-for-holidays-optional"></a>Etapa 4: configurar fluxos de chamada para feriados (opcional)

O atendente automático pode ter um fluxo de chamadas para cada [Feriado configurado](set-up-holidays-in-teams.md). Você pode adicionar até 20 conjuntos de férias a cada atendente automático. Cada conjunto de feriados pode conter até 10 intervalos de datas exclusivos. As datas de feriado devem ser exclusivas em todos os conjuntos de feriados que estão sendo adicionados ao atendente automático.

*Nova opção – A opção Forçar escuta pode ser habilitada, o que exige que os chamadores ouçam todas as opções de menu antes de fazer a seleção.*
 *Novas chaves - \* (asterisco) e \# (libra) agora podem ser usadas nas opções de menu.*

1. Na página Configurações de chamada de feriado, selecione **Adicionar**.

1. Digite um nome para essa configuração de feriado.

1. Na lista suspensa **Feriado** , escolha o feriado que você deseja usar.

1. Escolha o tipo de saudação que você deseja usar.

1. Escolha se deseja **Desconectar**, **Redirecionar** ou **Reproduzir opções de menu** a chamada.

    1. Se você optar por redirecionar, escolha o destino de roteamento de chamada para a chamada.
    1. Se você optar por reproduzir opções de menu, configure as **opções de menu Reproduzir**.

1. Selecione **Salvar**.

Repita o procedimento conforme necessário para cada feriado adicional.

Depois de adicionar todas as suas horas de férias, selecione **Avançar**.

## <a name="step-5-dial-scope"></a>[Etapa 5: Escopo de discagem](#tab/dial-scope)

## <a name="step-5-set-up-dial-scope-optional"></a>Etapa 5: configurar o escopo de discagem (opcional)

O *escopo de discagem* define quais usuários estão disponíveis no diretório quando um chamador usa discagem por nome ou discagem por extensão. O padrão de **Todos os usuários online** inclui todos os usuários da sua organização que são usuários online ou hospedados localmente usando Skype for Business Server.

Você pode incluir ou excluir usuários específicos selecionando **grupos de usuários personalizados** em **Incluir** ou **Excluir** e escolhendo um ou mais grupos do Microsoft 365, listas de distribuição ou grupos de segurança. Por exemplo, talvez você queira excluir executivos em sua organização do diretório de discagem.

Se um usuário estiver em ambas as listas, ele será excluído do diretório.

> [!NOTE]
> Pode levar até 36 horas para que um novo usuário tenha seu nome listado no diretório.

Depois de selecionar as opções de **escopo discar** , selecione **Avançar**.

## <a name="step-6-resource-accounts"></a>[Etapa 6: Contas de recursos](#tab/resource-accounts)

## <a name="step-6-set-up-resource-accounts-optional"></a>Etapa 6: Configurar contas de recursos (opcional)

Todos os atendentes automáticos devem ter uma conta de recurso associada.  Os atendentes automáticos de primeiro nível precisarão de pelo menos uma conta de recurso que tenha um número de serviço associado. Se desejar, você pode atribuir várias contas de recurso a um atendente automático, cada uma com um número de serviço separado.

Para adicionar uma conta de recurso, selecione **Adicionar conta** e pesquise a conta que você deseja adicionar. Selecione **Adicionar** e, em seguida, selecione **Adicionar**.

Depois de adicionar contas de recursos, selecione **Avançar**.

Para obter mais informações, consulte [Gerenciar contas de recursos do Teams](manage-resource-accounts.md).

---

## <a name="resources-for-complex-scenarios"></a>Recursos para cenários complexos

### <a name="external-phone-number-transfers---technical-details"></a>Transferências de número de telefone externas – detalhes técnicos

Consulte os [Pré-requisitos](plan-auto-attendant-call-queue.md#prerequisites) para permitir que os atendentes automáticos transfiram chamadas externamente.  Além disso

- Para uma conta de recurso com uma [licença de Plano de Chamada](calling-plans-for-office-365.md) ou número do [Operator Connect](operator-connect-plan.md) , o número de telefone de transferência externa deve ser inserido no formato E.164 (+[código do país][código da área][número de telefone]).

- Para uma conta de recurso com uma política de roteamento de voz online Telefonia do Microsoft Teams Licença e Roteamento Direto, o formato de número de telefone de transferência externa depende das configurações [do SBC (Controlador de Borda de Sessão).](direct-routing-connect-the-sbc.md)

O número de telefone de saída exibido é determinado da seguinte maneira:

- Para números de Plano de Chamada e Conexão de Operador, o número de telefone do chamador original é exibido.
- Para números de Roteamento Direto, o número enviado é baseado na configuração P-Asserted-Identity (PAI) no SBC, da seguinte maneira:
  - Se definido como Desabilitado, o número de telefone do chamador original será exibido. Desabilitado é a configuração padrão e recomendada.
  - Se definido como Habilitado, o número de telefone da conta de recurso será exibido.

Em um ambiente híbrido Skype for Business, para transferir uma chamada de atendimento automático para o PSTN, crie um novo usuário local com o encaminhamento de chamada definido para o número PSTN. O usuário deve estar habilitado para Enterprise Voice e ter uma política de voz atribuída. Para saber mais, confira [Transferência de chamada de atendente automático para PSTN](/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn).

### <a name="auto-attendant-diagnostic-tool"></a>Ferramenta de Diagnóstico do Atendente Automático

Se você for um administrador, poderá usar a seguinte ferramenta de diagnóstico para validar se um atendente automático pode receber chamadas:

1. Selecione **Executar testes** abaixo, o que preencherá o diagnóstico no Centro de Administração do Microsoft 365.

   > [!div class="nextstepaction"]
   > [Executar testes: Assistente Automático do Teams](https://aka.ms/TeamsAADiag)

2. No painel Executar diagnóstico, **insira** a Conta de Recurso no campo **Nome de usuário ou Email** e selecione Executar Testes.

3. Os testes identificarão configurações de conta de locatário, política ou recurso que estão impedindo o atendente automático de receber chamadas e também fornecerão etapas para corrigir quaisquer problemas identificados.

## <a name="related-articles"></a>Artigos relacionados

[Aqui está o que você obtém com o Teams Phone](./here-s-what-you-get-with-phone-system.md)

[Obter números de telefone de serviço](./getting-service-phone-numbers.md)

[Disponibilidade de Audioconferência e Planos de Chamadas por país e região](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[Uma introdução ao Windows PowerShell e ao Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
