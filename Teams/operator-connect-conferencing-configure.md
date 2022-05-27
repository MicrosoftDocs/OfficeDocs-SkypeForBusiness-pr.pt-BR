---
title: Configurar Conferência de conexão do operador
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.date: 09/30/2021
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: Saiba mais sobre como configurar o Conferência de conexão do operador.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: ade65551ad30c15fd209aa542781edce44bd76dd
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676023"
---
# <a name="configure-operator-connect-conferencing"></a>Configurar Conferência de conexão do operador

Este artigo fornece detalhes sobre como configurar Conferência de conexão do operador para sua organização e usuários.

Antes de configurar o Conferência de conexão do operador, leia [Plan for Conferência de conexão do operador](operator-connect-conferencing-plan.md) para obter informações sobre os benefícios e os requisitos de licenciamento.

Os tópicos abordados neste artigo incluem:

- [Configurar um operador](#set-up-an-operator)
- [Adquirir números para sua ponte Audioconferência dados](#acquire-numbers-for-your-audio-conferencing-bridge)
- [Alterar os números de telefone padrão incluídos nos convites de reunião dos usuários](#change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users)
- [Enviar chamadas de saída de Microsoft Teams reuniões por meio de um operador](#sending-outbound-calls-from-microsoft-teams-meetings-through-an-operator)
- [Gerenciar seus operadores](#manage-your-operators)
- [Números de versão de sua ponte Audioconferência dados](#release-numbers-from-your-audio-conferencing-bridge)
- [Informações adicionais sobre como gerenciar o Microsoft Audioconferência](#additional-information-on-managing-microsoft-audio-conferencing)

## <a name="set-up-an-operator"></a>Configurar um operador

Você pode configurar, editar e remover operadores no centro Teams administrador. No painel de navegação esquerdo, vá para **Operadores de > Voz**.

Para configurar um operador:

1. **Escolha um operador.** Na guia **Todos os operadores** , filtre os operadores disponíveis por região ou serviço para encontrar o operador certo para suas necessidades de voz. Em seguida, selecione o operador que você deseja usar. Por Conferência de conexão do operador, verifique se o operador tem **a Conferência** listada como um produto disponível.

2. **Selecionar países.** Em **Configurações do operador**, selecione os países que você deseja habilitar com o operador selecionado.

3. **Fornecer informações de contato** Suas informações de contato, incluindo seu nome completo e endereço de email, serão compartilhadas com seu operador. Você pode alterar essas informações mais tarde. Além disso, você precisará fornecer o tamanho da empresa, com a opção de fornecer seu número de telefone. Os operadores usam essas informações para entrar em contato com você com mais detalhes sobre Conferência de conexão do operador.

4. Aceite o aviso de transferência de dados.

5. **Adicione seu operador.** Selecione **Adicionar como meu operador** para salvar.

## <a name="acquire-numbers-for-your-audio-conferencing-bridge"></a>Adquirir números para sua ponte Audioconferência dados

A ponte de Audioconferência sua organização inclui números de telefone disponíveis para todos os usuários em sua organização ingressarem Microsoft Teams reuniões com números de telefone PSTN. Você pode ver os números de telefone associados à ponte de Audioconferência da sua organização no Centro de Teams Administração em **Reuniões > Pontes de Conferência**.

Para adquirir números de telefone para sua ponte Audioconferência, siga estas etapas:

1. **Audioconferência assinatura padrão ou Conferência de conexão do operador licença.** Os usuários que precisam Conferência de conexão do operador para ingressar nas reuniões que organizam precisam ter uma licença de assinatura Audioconferência Standard ou uma licença Conferência de conexão do operador atribuída a eles. Para obter mais informações, [consulte Plan for Conferência de conexão do operador](operator-connect-conferencing-plan.md).

2. **Adquirir números.** Acesse o site da sua operadora para solicitar e adquirir números de telefone. Para obter uma lista de sites de operadores, vá para o [Microsoft 365 Conexão do operador diretório](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory). Você precisará fornecer sua ID de locatário. Se você não souber sua ID de locatário, consulte [Localizar sua ID Microsoft 365 locatário.](/onedrive/find-your-office-365-tenant-id) Depois que o operador concluir o pedido, ele carregará números em seu locatário. Você pode exibir os números e o provedor no centro de Teams de administração, indo para **Voz > Telefone números**.

3. **Atribua números à sua Audioconferência ponte.** Você pode atribuir números à sua ponte Audioconferência do centro de administração do Teams em **Reuniões > Pontes de Conferência > Adicionar**. Para obter mais informações, [consulte Alterar os números de telefone em sua Audioconferência ponte](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).

>[!NOTE]
>Não é possível atribuir Conferência de conexão do operador como números padrão de uma ponte. Depois que um número de telefone for atribuído à sua ponte do Audioconferência, o número será listado na página Localizar um número **local** incluído nos convites de reunião de usuários em sua organização com uma licença do Audioconferência ou uma licença Conferência de conexão do operador.
>
>Para rotear chamadas de saída por meio de um operador, consulte o envio de chamadas de Teams [**reuniões**](#sending-outbound-calls-from-microsoft-teams-meetings-through-an-operator) por meio de uma seção de operador mais abaixo neste artigo.

## <a name="change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users"></a>Alterar os números de telefone padrão incluídos nos convites de reunião dos usuários

 Esta etapa é opcional.

Os números de telefone padrão de um usuário são aqueles incluídos em seus convites de reunião quando agendam uma reunião. Você pode atualizar os números de telefone incluídos nos convites de reunião de usuários no centro de Teams Administração **em Usuários > Gerenciar usuários**. Para atualizar os números de telefone incluídos nos convites de reunião de usuários, selecione o usuário e  selecione **Editar Audioconferência** seção.

Depois que as alterações forem aplicadas, os novos convites de reunião dos organizadores incluirão os novos números de telefone padrão. No entanto, os convites de reunião existentes que foram agendados antes da alteração manterão os números padrão originais.

## <a name="sending-outbound-calls-from-microsoft-teams-meetings-through-an-operator"></a>Enviar chamadas de saída de Microsoft Teams reuniões por meio de um operador

Se você tiver uma assinatura do Microsoft Audioconferência Standard ou uma licença do Conferência de conexão do operador, poderá configurar o serviço Audioconferência para rotear todas ou um conjunto de chamadas de saída de reuniões do Teams por meio de seu operador configurando um Audioconferência de roteamento.

>[!NOTE]
>Com uma Conferência de conexão do operador, as chamadas de saída só podem passar pelo operador. Se você tiver Conferência de conexão do operador licenças, precisará configurar o serviço conforme descrito abaixo para habilitar chamadas de saída de reuniões Teams números de telefone.

Você pode aplicar Audioconferência roteamento no nível do usuário, o que significa que seu operador roteia apenas as chamadas de saída de Teams reuniões organizadas por usuários com a política associada. Você também pode aplicar essas políticas no nível global, o que significa que seu operador roteia chamadas de saída de Teams reuniões organizadas por todos os usuários em sua organização.

Usando o PowerShell, crie a nova política de roteamento Audioconferência organização. Para especificar um operador como a rota primária para chamadas de Teams reuniões, siga as etapas abaixo usando os comandos do PowerShell indicados:

1. [Etapa 1: Adicionar uma nova cadeia de caracteres à política de Uso PSTN Online](#step-1-add-a-new-string-to-the-online-pstn-usage-policy)
2. [Etapa 2: Criar uma nova política de Rota de Voz Online](#step-2-create-a-new-online-voice-route-policy)
3. [Etapa 3: Criar uma nova política de roteamento de Audioconferência online](#step-3-create-a-new-online-audio-conferencing-routing-policy)
4. [Etapa 4: Atribuir a nova política aos usuários](#step-4-assign-the-new-policy-to-users)

### <a name="step-1-add-a-new-string-to-the-online-pstn-usage-policy"></a>Etapa 1: Adicionar uma nova cadeia de caracteres à política de Uso PSTN Online

Leia [Set-CsOnlinePstnUsage para](/powershell/module/skype/set-csonlinepstnusage) obter mais informações sobre como usar esse cmdlet.

```powershell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

### <a name="step-2-create-a-new-online-voice-route-policy"></a>Etapa 2: Criar uma nova política de Rota de Voz Online

Leia [Set-CsOnlineVoiceRoute para](/powershell/module/skype/set-csonlinevoiceroute) obter mais informações sobre como usar esse cmdlet.

```powershell
New-CsOnlineVoiceRoute -Identity "International" -NumberPattern "\d+" -OnlinePstnUsages "International" -BridgeSourcePhoneNumber <an Operator Connect Conferencing number assigned to your Audio Conferencing bridge>
```

### <a name="step-3-create-a-new-online-audio-conferencing-routing-policy"></a>Etapa 3: Criar uma nova política de roteamento de Audioconferência online

```powershell
New-CsOnlineAudioConferencingRoutingPolicy "International Policy" -OnlinePstnUsages "International"
```

### <a name="step-4-assign-the-new-policy-to-users"></a>Etapa 4: Atribuir a nova política aos usuários

```powershell
Grant-CsOnlineAudioConferencingRoutingPolicy -Identity <identity of the organizer of the meeting> -PolicyName "International Policy"
```

>[!NOTE]
>Para definir uma política Audioconferência roteamento como global e aplicá-la a todos os usuários em sua organização, ``-Global`` você pode usar o parâmetro em vez do ``-Identity`` parâmetro. Por exemplo, ``Grant-CsOnlineAudioConferencingRoutingPolicy -Global -PolicyName "International Policy"``.

Quando você cria uma política de roteamento do Audioconferência e a aplica a um usuário, ``BridgeSourcePhoneNumber`` o operador que fornece o número de telefone especificado nas rotas de parâmetro Teams chamadas de saída para números de telefone PSTN. Além disso, o parâmetro ``BridgeSourcePhoneNumber`` especifica o número de telefone a ser usado como o número de telefone de identificação de linha de chamada de chamadas de saída para números de telefone PSTN.

O padrão especificado no é de ``NumberPattern`` formulário regex e especifica quais chamadas rotear por meio do operador. O ``"\d+"`` padrão no exemplo acima corresponde a todas as chamadas de saída de Teams reuniões. Você também pode definir o parâmetro NumberPattern  ``"^\+1(425|206)(\d{7})$"``como , que corresponde a números discados com os seguintes formatos: +1 425 XXX XX XX ou +1 206 XXX XX XX ou ``"^\+1(\d{10})$"``, que corresponde a números discados com o seguinte formato: +1 425 XXX XX XX.

Depois de atribuir uma política de roteamento do Audioconferência a um usuário, todas as chamadas de suas reuniões para um número de telefone que corresponda ao regex especificado em suas rotas de política de roteamento do Audioconferência  por meio de sua operadora, incluindo Ligar para  mim em chamadas e chamadas iniciadas por meio da opção Convidar alguém ou discar uma opção de reunião de número.

## <a name="manage-your-operators"></a>Gerenciar seus operadores

Na guia **Meus operadores** , você pode exibir seus operadores, seu status e fazer as seguintes alterações em suas seleções:

- Gerenciar serviços de operador por país
- Suspender um operador
- Remover um operador

>[!NOTE]
>Antes de remover um operador de sua organização ou de um país, você deve remover todos os números de telefone atribuídos aos usuários e sua ponte Audioconferência e entrar em contato com o operador para liberar os números.

## <a name="release-numbers-from-your-audio-conferencing-bridge"></a>Números de versão de sua ponte Audioconferência dados

Para liberar números de telefone da ponte Audioconferência do centro de administração do Teams, consulte Etapas quando você está cancelando a atribuição de um número de telefone de serviço para uma ponte de conferência em Alterar os números de telefone na ponte [Audioconferência](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge).

## <a name="additional-information-on-managing-microsoft-audio-conferencing"></a>Informações adicionais sobre como gerenciar o Microsoft Audioconferência

Para obter informações adicionais sobre como gerenciar o Microsoft Audioconferência para sua organização, consulte os seguintes artigos:

- Gerenciando as configurações de serviço do Microsoft Audioconferência para sua organização: gerenciar as configurações de Audioconferência para sua organização [no Microsoft Teams](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md)

- Gerenciando a configuração Audioconferência serviço microsoft dos usuários em sua organização: gerenciar as configurações de Audioconferência para um usuário [no Microsoft Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)

- Alterando os idiomas do atendedor automático de seus Audioconferência de telefone: defina idiomas de atendedor automático [para Audioconferência no Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)
