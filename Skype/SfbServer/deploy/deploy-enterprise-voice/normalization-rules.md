---
title: Criar ou modificar uma regra de normalização em Skype for Business
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e8547d7b-f74d-4a73-9a7d-df20d7a87fcd
description: 'Resumo: saiba como definir, criar e modificar uma regra de normalização em Skype for Business Server.'
ms.openlocfilehash: f2f47859687a7c3919e59979c259f317ef6a3102
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62387269"
---
# <a name="create-or-modify-a-normalization-rule-in-skype-for-business"></a>Criar ou modificar uma regra de normalização em Skype for Business

**Resumo:** Saiba como definir, criar e modificar uma regra de normalização em Skype for Business Server.

Definir, criar e modificar regras de normalização em Skype for Business Server.

### <a name="to-define-a-normalization-rule-by-using-build-a-normalization-rule"></a>Para definir uma regra de normalização usando Build a Normalization Rule

1. Abrir Skype for Business Server Painel de Controle

2. (Opcional) Siga as etapas em [Create or modify a dial plan in Skype for Business Server](dial-plans.md) through step 11 or [Modify a Dial Plan](/previous-versions/office/lync-server-2013/lync-server-2013-modify-a-dial-plan) through step 10.

3. Em **Nova Regra de Normalização** ou Editar Regra de **Normalização**, digite um nome que descreve o padrão de número que está sendo normalizado em **Name** (por exemplo, 5DigitExtension).

4. (Opcional) Em **Descrição**, digite uma descrição da regra de normalização (por exemplo, "Converte extensões de cinco dígitos").

5. Em **Compilar uma Regra de Normalização**, digite valores nos campos a seguir:

   - **Dígitos in-locar** (Opcional) Especifique os dígitos principais dos números discados que você deseja que o padrão corresponder. Por exemplo, digite425 se quiser que o padrão corresponder aos números discados começando com 425.

   - **Comprimento** Especifique o número de dígitos no padrão correspondente e selecione se você deseja que o padrão corresponde a esse comprimento exatamente, corresponder a números discados que têm pelo menos esse tamanho ou corresponder a números discados de qualquer comprimento.

   - **Dígitos a serem removidos** (Opcional) Especifique o número de dígitos inativos a serem removidos dos números discados que você deseja que o padrão corresponder.

   - **Dígitos a serem adicionados** (Opcional) Especifique dígitos a serem adicionados aos números discados que você deseja que o padrão corresponder.

     Os valores inseridos nesses campos são refletidos em **Padrão a ser correspondido** e **Regra de conversão**. Por exemplo, se você deixar **dígitos** in-locar vazios,  digite7 no campo Comprimento e selecione Exatamente e especifique 0 em **Dígitos** a ser removido, a expressão regular resultante no **Padrão** a ser corresponder será:

     ^(\d{7})$

6. Em **Regra de conversão**, especifique um padrão para o formato de números de telefone E.164 convertido da seguinte maneira:

   - Um valor que representa o número de dígitos especificado no padrão de correspondência. Por exemplo, se o padrão correspondente for ^(\d{7})$, $1 na regra de conversão representará números discados de 7 dígitos.

   - (Opcional) Digite um valor nos **Dígitos** para adicionar campo para especificar dígitos a serem acrescentados ao número convertido (por exemplo, +1425).

     Por exemplo, se **Pattern to match** contiver^(\d{7})$ como o padrão para números discados e a regra de conversão contiver+1425$1 como o padrão para números de telefone E.164, a regra normaliza 5550100 a +14255550100.

7. (Opcional) Se a regra de normalização resultar em um número de telefone interno em sua organização, selecione **Extensão interna**.

8. (Opcional) Insira um número para testar a regra de normalização e clique em **Ir**. Os resultados do teste são exibidos em **Inserir um número para testar**.

    > [!NOTE]
    > É possível salvar uma regra de normalização que não passou ainda no teste e reconfigurá-la mais tarde. Para obter detalhes, consulte [Test Voice Routing](/previous-versions/office/lync-server-2013/lync-server-2013-test-voice-routing).

9. Clique em **OK** para salvar a regra de normalização.

10. Clique em **OK** para salvar o plano de discagem.

11. Na página **Plano de Discagem**, clique em **Confirmar** e clique em **Confirmar tudo**.

    > [!NOTE]
    > Sempre que criar ou alterar uma regra de normalização, você deve executar o comando **Confirmar todos** para publicar a alteração na configuração. Para obter detalhes, [consulte Publicar alterações pendentes na](voice-route-config-changes.md) configuração de roteamento de voz Skype for Business na documentação Operações.

### <a name="to-define-a-normalization-rule-manually"></a>Para definir uma regra de normalização manualmente

1. Abrir Skype for Business Server Painel de Controle

2. (Opcional) Siga as etapas em [Criar ou modificar um plano de discagem em Skype for Business Server](dial-plans.md).

3. Em **Nova Regra de Normalização** ou Editar Regra de **Normalização**, digite um nome que descreve o padrão de número que está sendo normalizado em **Name** (por exemplo, nomeia a regra de normalização5DigitExtension).

4. (Opcional) No campo **Descrição**, digite uma descrição da regra de normalização (por exemplo, "Traduzir extensões de 5 dígitos").

5. Em **Criar uma regra de normalização**, clique em **Editar**.

6. Digite o seguinte em **Digitar uma expressão regular**:

   - Em **Corresponder este padrão**, especifique o padrão que você deseja usar para coincidir com o número de telefone discado.

   - Em **Regra de tradução**, especifique um padrão para o formato dos números de telefone E.164 traduzidos.

     Por exemplo, se você inserir ^(\d{7})$ em  Corresponder a esse padrão e+1425$1 na regra de conversão **, a** regra normaliza 5550100 para +14255550100.

7. (Opcional) Se a regra de normalização resulta em um número de telefone interno à sua organização, selecione **Extensão interna**.

8. (Opcional) Insira um número para testar a regra de normalização e clique em **Ir**. Os resultados do teste são exibidos em **Inserir um número para testar**.

9. Clique em **OK** para salvar a regra de normalização.

10. Clique em **OK** para salvar o plano de discagem.

11. Na página **Plano de Discagem**, clique em **Confirmar** e clique em **Confirmar tudo**.

    > [!NOTE]
    > Sempre que criar ou alterar uma regra de normalização, você deve executar o comando **Confirmar todos** para publicar a alteração na configuração. Para obter detalhes, [consulte Publicar alterações pendentes na](voice-route-config-changes.md) configuração de roteamento de voz Skype for Business na documentação Operações.