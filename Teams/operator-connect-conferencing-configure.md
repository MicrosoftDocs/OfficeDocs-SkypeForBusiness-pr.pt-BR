---
title: Configurar conferência Conexão operador
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
description: Saiba mais sobre como configurar o Operador Conexão Conferência.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 87358190d919519b39494576a05235df26ad4c7a
ms.sourcegitcommit: be8b820caf4b5a1a91ad444ba93da1df20bf63ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/01/2021
ms.locfileid: "61257492"
---
# <a name="configure-operator-connect-conferencing"></a>Configurar conferência Conexão operador

Este artigo detalha como configurar a Conferência Conexão Operador para sua organização e usuários.

Antes de configurar a Conferência Conexão Operador, leia [Plan for Operator Conexão Conferencing](operator-connect-conferencing-plan.md) para obter informações sobre benefícios e requisitos de licenciamento.

Os tópicos abordados neste artigo incluem:

- [Configurar um operador](#set-up-an-operator)
- [Adquirir números para sua ponte de Audioconferência](#acquire-numbers-for-your-audio-conferencing-bridge)
- [Alterar os números de telefone padrão incluídos nos convites de reunião dos usuários](#change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users)
- [Enviando chamadas de saída de Microsoft Teams reuniões por meio de um operador](#sending-outbound-calls-from-microsoft-teams-meetings-through-an-operator)
- [Gerenciar seus operadores](#manage-your-operators)
- [Números de versão de sua ponte de Audioconferência](#release-numbers-from-your-audio-conferencing-bridge)
- [Informações adicionais sobre como gerenciar a Audioconferência da Microsoft](#additional-information-on-managing-microsoft-audio-conferencing)

## <a name="set-up-an-operator"></a>Configurar um operador

Você pode configurar, editar e remover operadores no Teams de administração. No painel de navegação esquerdo, vá para **Voice > Operators**.

Para configurar um operador:

1. **Escolha um operador.**   Na guia  **Todos os operadores,** filtre operadores disponíveis por região ou serviço para   encontrar o operador certo para suas necessidades de voz. Em seguida, selecione o operador que você deseja usar. Para Conferência Conexão operador, verifique se seu operador tem **Conferência** listada como um produto disponível.

2. **Selecione países.**   Em  **Configurações de operador**, selecione os países que você deseja habilitar com o operador selecionado.

3. **Fornecer informações de contato**   Suas informações de contato, incluindo seu nome completo e endereço de email, serão compartilhadas com sua operadora. Você pode alterar essas informações mais tarde. Além disso, você precisará fornecer o tamanho da empresa, com a opção de fornecer seu número de telefone. Os operadores usam essas informações para entrar em contato com você com mais detalhes sobre a conferência Conexão Operador.

4. Aceite o aviso de transferência de dados.

5. **Adicione seu operador.**   Selecione  **Adicionar como meu operador** para   salvar.

## <a name="acquire-numbers-for-your-audio-conferencing-bridge"></a>Adquirir números para sua ponte de Audioconferência

A ponte de Audioconferência da sua organização inclui números de telefone disponíveis para todos os usuários em sua organização para participar de reuniões Microsoft Teams com números de telefone PSTN. Você pode ver os números de telefone associados à ponte de Audioconferência da sua organização no Centro de Administração Teams em **Reuniões > Pontes de Conferência.**

Para adquirir números de telefone para sua ponte de Audioconferência, siga estas etapas:

1. **Assinatura padrão de audioconferência ou licença de Conexão de Conferência.** Os usuários que precisam de números de Conferência Conexão Operador para ingressar nas reuniões que organizam precisam ter uma licença de assinatura Padrão de Audioconferência ou uma licença de Conferência Conexão Operador atribuída a eles. Para obter mais informações, consulte [Plan for Operator Conexão Conferencing](operator-connect-conferencing-plan.md).

2. **Adquirir números.**   Acesse o site da sua operadora para solicitar e adquirir números de telefone. Para uma lista de sites de operador, acesse o diretório Microsoft 365 [Operator Conexão.](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory) Você precisará fornecer sua ID de locatário. Se você não conhece sua ID de locatário, consulte [Find your Microsoft 365 tenant ID](/onedrive/find-your-office-365-tenant-id). Depois que o operador concluir o pedido, ele carregará números no locatário. Você pode exibir os números e o provedor no centro de administração Teams, indo para **Voz > Telefone números**.

3. **Atribua números à sua ponte de Audioconferência.** Você pode atribuir números à sua ponte de Audioconferência Teams centro de administração em **Reuniões > Pontes** de Conferência > Adicionar . Para obter mais informações, [consulte Alterar os números de telefone em sua ponte de Audioconferência](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).

>[!NOTE]
>Não é possível atribuir números de conferência Conexão operador como números padrão de uma ponte. Depois que um número de telefone é atribuído à sua ponte de Audioconferência, o número será listado na página Encontrar um número **local** incluído nos convites de reunião de usuários em sua organização com uma licença de Audioconferência ou uma licença de Conferência Conexão Operador.
>
>Para rotear chamadas de saída através de um operador, consulte o [**envio**](#sending-outbound-calls-from-microsoft-teams-meetings-through-an-operator) de chamadas de saída de reuniões Teams por meio de uma seção de operador mais abaixo neste artigo.

## <a name="change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users"></a>Alterar os números de telefone padrão incluídos nos convites de reunião dos usuários

 Esta etapa é opcional.

Os números de telefone padrão de um usuário são os incluídos em seus convites de reunião ao agendar uma reunião. Você pode atualizar os números de telefone incluídos nos convites de reunião de usuários no Centro de Administração Teams em **Usuários > Gerenciar usuários**. Para atualizar os números de telefone incluídos nos convites de reunião dos usuários, selecione o usuário e selecione **Editar** na seção **Audioconferência.**

Depois que as alterações foram aplicadas, os novos convites de reunião dos organizadores incluirão os novos números de telefone padrão. No entanto, os convites de reunião existentes que foram agendados antes da alteração manterão os números padrão originais.

## <a name="sending-outbound-calls-from-microsoft-teams-meetings-through-an-operator"></a>Enviando chamadas de saída de Microsoft Teams reuniões por meio de um operador

Se você tiver uma assinatura do Microsoft Audioconferência Standard ou uma licença de Conferência Conexão Operador, poderá configurar o serviço de Audioconferência para rotear todas ou um conjunto de chamadas de saída de reuniões de Teams por meio de sua operadora configurando uma política de Roteamento de Audioconferência.

>[!NOTE]
>Com uma licença de Conexão de conferência de operador, as chamadas de saída só podem passar por sua operadora. Se você tiver licenças Conexão de Conferência de Operador, será necessário configurar o serviço conforme descrito abaixo para habilitar chamadas de saída de reuniões Teams para números de telefone.

Você pode aplicar políticas de Roteamento de Audioconferência no nível do usuário, o que significa que sua operadora roteia apenas as chamadas de saída de reuniões Teams organizadas pelos usuários com a política associada. Você também pode aplicar essas políticas a nível global, o que significa que sua operadora encaminha chamadas de Teams reuniões organizadas por todos os usuários em sua organização.

Usando o PowerShell, crie a nova política de Roteamento de Audioconferência da sua organização. Para especificar um operador como a rota primária para chamadas de Teams reuniões de Teams, siga as etapas abaixo usando os comandos do PowerShell indicados:

1. [Etapa 1: Adicionar uma nova cadeia de caracteres à política de Uso PSTN Online](#step-1-add-a-new-string-to-the-online-pstn-usage-policy)
2. [Etapa 2: Criar uma nova política de Rota de Voz Online](#step-2-create-a-new-online-voice-route-policy)
3. [Etapa 3: Criar uma nova política de Roteamento de Audioconferência Online](#step-3-create-a-new-online-audio-conferencing-routing-policy)
4. [Etapa 4: Atribuir a nova política aos usuários](#step-4-assign-the-new-policy-to-users)

### <a name="step-1-add-a-new-string-to-the-online-pstn-usage-policy"></a>Etapa 1: Adicionar uma nova cadeia de caracteres à política de Uso PSTN Online

Leia [Set-CsOnlinePstnUsage](/powershell/module/skype/set-csonlinepstnusage) para obter mais informações sobre como usar este cmdlet.

```powershell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

### <a name="step-2-create-a-new-online-voice-route-policy"></a>Etapa 2: Criar uma nova política de Rota de Voz Online

Leia [Set-CsOnlineVoiceRoute para](/powershell/module/skype/set-csonlinevoiceroute) obter mais informações sobre como usar este cmdlet.

```powershell
New-CsOnlineVoiceRoute -Identity "International" -NumberPattern "\d+" -OnlinePstnUsages "International" -BridgeSourcePhoneNumber <an Operator Connect Conferencing number assigned to your Audio Conferencing bridge>
```

### <a name="step-3-create-a-new-online-audio-conferencing-routing-policy"></a>Etapa 3: Criar uma nova política de Roteamento de Audioconferência Online

```powershell
New-CsOnlineAudioConferencingRoutingPolicy "International Policy" -OnlinePstnUsages "International"
```

### <a name="step-4-assign-the-new-policy-to-users"></a>Etapa 4: Atribuir a nova política aos usuários

```powershell
Grant-CsOnlineAudioConferencingRoutingPolicy -Identity <identity of the organizer of the meeting> -PolicyName "International Policy”
```

>[!NOTE]
>Para definir uma política de Roteamento de Audioconferência como global e aplicá-la a todos os usuários em sua organização, você pode usar o parâmetro ``-Global`` em vez do ``-Identity`` parâmetro. Por exemplo, ``Grant-CsOnlineAudioConferencingRoutingPolicy -Global -PolicyName "International Policy”`` .

Ao criar uma política de Roteamento de Audioconferência e aplicá-la a um usuário, a operadora que fornece o número de telefone especificado nos parâmetros Teams chamadas de saída para números de telefone ``BridgeSourcePhoneNumber`` PSTN. Além disso, o parâmetro especifica o número de telefone a ser usado como o número de telefone de identificação de linha de chamada de chamadas de saída para números de telefone ``BridgeSourcePhoneNumber`` PSTN.

O padrão especificado no é de formulário regex e especifica quais chamadas ``NumberPattern`` encaminhar através de seu operador. O padrão no exemplo acima corresponde a todas as chamadas de saída ``"\d+"`` de Teams reuniões. Você também pode definir o parâmetro NumberPattern como , que corresponde aos números discados com os seguintes formatos: +1 425 XXX XX XX ou +1 206 XXX XX ou , que corresponde aos números discados com o seguinte  ``“^\+1(425|206)(\d{7})$”`` ``“^\+1(\d{10})$”`` formato: +1 425 XXX XX.

Depois de atribuir uma política de Roteamento de Audioconferência a um usuário, todas as chamadas de suas reuniões para um número de telefone que corresponde ao regex especificado em suas rotas de política de Roteamento de Audioconferência através de sua operadora, incluindo **Chamar-me** em chamadas e chamadas iniciadas por meio da opção Convidar alguém ou discar **uma opção** de reunião de número.

## <a name="manage-your-operators"></a>Gerenciar seus operadores

Na guia **Meus operadores,** você pode exibir seus operadores, seu status e fazer as   seguintes alterações em suas seleções:

- Gerenciar serviços de operador por país
- Suspender um operador
- Remover um operador

>[!NOTE]
>Antes de remover um operador de sua organização ou de um país, você deve remover todos os números de telefone atribuídos aos usuários e sua ponte de Audioconferência e entrar em contato com o operador para liberar os números.

## <a name="release-numbers-from-your-audio-conferencing-bridge"></a>Números de versão de sua ponte de Audioconferência

Para liberar números de telefone de sua ponte de Audioconferência do centro de administração do Teams, consulte Etapas quando você está **desaignando** um número de telefone de serviço para uma ponte de conferência em Alterar os números de telefone em sua ponte de [Audioconferência](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge).

## <a name="additional-information-on-managing-microsoft-audio-conferencing"></a>Informações adicionais sobre como gerenciar a Audioconferência da Microsoft

Para obter informações adicionais sobre como gerenciar a Audioconferência da Microsoft para sua organização, consulte os seguintes artigos:

- Gerenciando as configurações do serviço de Audioconferência da Microsoft para sua organização: Gerenciar as configurações de [Audioconferência](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md) para sua organização em Microsoft Teams

- Gerenciando a configuração do serviço de Audioconferência da Microsoft dos usuários em sua organização: Gerenciar as configurações de [Audioconferência](manage-the-audio-conferencing-settings-for-a-user-in-teams.md) para um usuário em Microsoft Teams

- Alterando os idiomas de atendimento automático dos números de telefone de Audioconferência: Definir idiomas de atendimento automático [para Audioconferência em Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)
