---
title: Criar um modelo de reunião personalizado no Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ralphmaamari
audience: admin
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- m365solution-compliantmeetings
- m365initiative-meetings
- highpri
appliesto:
- Microsoft Teams
description: Saiba como os administradores do Microsoft Teams podem criar um modelo de reunião personalizado para definir ou impor as configurações do organizador da reunião para melhorar a segurança e a conformidade da reunião.
ms.openlocfilehash: ec9e836474032d5bb9fde0aed6c81a231788d1bf
ms.sourcegitcommit: ca4d1011f3d62af203145431f0b19065ad81601b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/13/2023
ms.locfileid: "69800268"
---
# <a name="create-a-custom-meeting-template-in-microsoft-teams"></a>Criar um modelo de reunião personalizado no Microsoft Teams

[!INCLUDE[Teams Premium](includes/teams-premium-ecm.md)]

Os modelos de reunião personalizados do Microsoft Teams (um recurso Teams Premium) permitem especificar valores para muitas das configurações de reunião disponíveis para os organizadores da reunião. Os modelos podem configurar configurações que os organizadores da reunião podem alterar ou podem bloquear as configurações para que os organizadores da reunião não possam alterá-las. Para obter mais informações sobre modelos de reunião personalizados, consulte [Visão geral dos modelos de reunião personalizados no Microsoft Teams](custom-meeting-templates-overview.md).

Você pode criar até 50 modelos personalizados. Consulte [Gerenciar modelos de reunião no Microsoft Teams](manage-meeting-templates.md) para obter informações sobre como gerenciar quais modelos estão disponíveis para seus usuários.

Para cada opção no modelo, você pode definir o seguinte:

- **Valor padrão** – esse é o valor que é aplicado a uma reunião quando o modelo é usado.
- **Visível** – isso determina se o organizador da reunião pode ver essa configuração nas opções de reunião. 
- **Status de bloqueio** – isso determina se o organizador da reunião pode alterar a configuração definida pelo modelo. Se a configuração estiver bloqueada, o organizador da reunião não poderá alterá-la.

Para criar um modelo de reunião personalizado

1. No centro de administração do Teams, expanda **Reuniões** e selecione **Modelos de reunião**.
1. Selecione **Adicionar**
1. Digite um nome e uma descrição para o modelo.
1. Escolha as configurações que você deseja usar para este modelo. (Confira as seções abaixo para obter descrições de cada configuração.)
1. Para impedir que o organizador da reunião altere uma configuração, selecione a configuração e selecione **bloquear**.
1. Para impedir que o organizador da reunião veja uma configuração, selecione a configuração e selecione **Ocultar**.
1. Selecione **Salvar**.

Depois que o modelo for criado, pode levar até 24 horas para estar disponível para seus usuários.

#### <a name="security"></a>Segurança

|Configuração|Descrição|
|:------|:----------|
|Rótulo de confidencialidade|Especifica o rótulo de confidencialidade da reunião a ser usado para a reunião. Observe que o rótulo de confidencialidade pode substituir determinadas configurações no modelo.|
|Quem pode ignorar o lobby?|Especifica quem pode ignorar o lobby e ingressar diretamente na reunião.|
|Pessoas discagem pode ignorar o lobby|Especifica se as pessoas que ligam por telefone podem ignorar o lobby e ingressar na reunião diretamente.|
|Notificar quando os chamadores ingressarem e saírem|Especifique se você deseja que um som seja reproduzido quando as pessoas que ligam por telefone ingressarem ou saírem da reunião.|
|Habilitar a criptografia de ponta a ponta da reunião|Especifique se deseja que a reunião use criptografia de ponta a ponta. A gravação e a transcrição não funcionarão se isso estiver ativado.|
|Aplicar uma marca d'água ao conteúdo compartilhado|Especifica se uma marca d'água é sobreposta no conteúdo compartilhado na tela na reunião.|
|Aplicar uma marca d'água ao feed de vídeo de todos|Especifica se uma marca d'água é sobreposta nos feeds de vídeo dos participantes na reunião.|

#### <a name="audio-and-video"></a>Áudio e vídeo

|Configuração|Descrição|
|:------|:----------|
|Permitir microfone para participantes|Quando **Ativado**, os participantes podem desmutar.|
|Permitir câmera para participantes|Quando **ativado**, os participantes podem ativar suas câmeras.|

#### <a name="recording-and-transcription"></a>Gravação e transcrição

|Configuração|Descrição|
|:------|:----------|
|Registrar reuniões automaticamente|Quando **as** reuniões on são registradas automaticamente.|
|Quem pode gravar reuniões?|Especifica se as reuniões podem ser gravadas apenas por organizadores ou por organizadores e apresentadores.|

#### <a name="meeting-engagement"></a>Compromisso de Reunião

|Configuração|Descrição|
|:------|:----------|
|Os participantes podem conversar|Especifica se o chat da reunião está disponível. Também pode ser usado para impedir o chat antes e depois da reunião.|
|Os participantes podem usar reações|Especifica se os participantes podem usar reações na reunião. Isso deve estar **ativado** para que o recurso de mão de elevação funcione.|
|Habilitar q&A|Especifica se os participantes podem usar o recurso Q&A para fazer perguntas durante a reunião.|
|Gerenciar o que os participantes veem|Quando **Ativado**, os organizadores da reunião podem visualizar e aprovar o conteúdo que está sendo compartilhado na tela antes que outros participantes da reunião possam vê-lo.|

## <a name="related-topics"></a>Tópicos relacionados

[Visão geral dos modelos de reunião personalizados no Microsoft Teams](custom-meeting-templates-overview.md)

[Use modelos de reunião do Teams, rótulos de confidencialidade e políticas de administrador juntos](meeting-templates-sensitivity-labels-policies.md)

[Configurar reuniões do Teams com três camadas de proteção](configure-meetings-three-tiers-protection.md)
