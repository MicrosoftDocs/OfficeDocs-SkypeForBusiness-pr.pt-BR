---
title: Criar ou modificar uma regra de normalização no Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e8547d7b-f74d-4a73-9a7d-df20d7a87fcd
description: 'Resumo: saiba como definir, criar e modificar uma regra de normalização no Skype for Business Server.'
ms.openlocfilehash: 4739bdb50e0a76c088cb6129539438c1ac6d795a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34306147"
---
# <a name="create-or-modify-a-normalization-rule-in-skype-for-business"></a>Criar ou modificar uma regra de normalização no Skype for Business

**Resumo:** Saiba como definir, criar e modificar uma regra de normalização no Skype for Business Server.

Definir, criar e modificar regras de normalização no Skype for Business Server.

### <a name="to-define-a-normalization-rule-by-using-build-a-normalization-rule"></a>Para definir uma regra de normalização usando Compilar uma Regra de Normalização

1. Abrir o painel de controle do Skype for Business Server

2. Adicionais Siga as etapas em [criar ou modificar um plano de discagem no Skype for Business Server](dial-plans.md) por meio da etapa 11 ou [modificar um plano de discagem](https://technet.microsoft.com/library/a91f02df-cf60-40cf-82fe-e0342c118b91.aspx) por meio da etapa 10.

3. Em **nova regra** de normalização ou **Editar regra**de normalização, digite um nome que descreva o padrão de número que está normalizado em **nome** (por exemplo, 5DigitExtension).

4. (Opcional) Em **Descrição**, digite uma descrição da regra de normalização (por exemplo, "Converte extensões de cinco dígitos").

5. Em **Compilar uma Regra de Normalização**, digite valores nos campos a seguir:

   - **Dígitos iniciais** Adicionais Especifique os dígitos à esquerda dos números discados para os quais você deseja que o padrão corresponda. Por exemplo, type425 se quiser que o padrão corresponda a números discados começando com 425.

   - **Comprimento** Especifique o número de dígitos no padrão de correspondência e selecione se deseja que o padrão corresponda exatamente a esse comprimento, corresponda aos números discados que tenham pelo menos esse comprimento ou coincidam com os números discados de qualquer comprimento.

   - **Dígitos a serem removidos** Adicionais Especifique o número de dígitos iniciais a serem removidos dos números discados para os quais você deseja que o padrão corresponda.

   - **Dígitos a serem adicionados** Adicionais Especifique os dígitos a serem adicionados aos números discados para os quais você deseja que o padrão corresponda.

     Os valores inseridos nesses campos são refletidos em **Padrão a ser correspondido** e **Regra de conversão**. Por exemplo, se você deixar os **dígitos iniciais** vazios, type7 no campo **comprimento** e selecionar **exatamente**e especificar 0 em **dígitos a remover**, a expressão regular resultante no **padrão a ser CORRESP** será:

     ^ (\d{7}) $

6. Em **Regra de conversão**, especifique um padrão para o formato de números de telefone E.164 convertido da seguinte maneira:

   - Um valor que representa o número de dígitos especificado no padrão de correspondência. Por exemplo, se o padrão correspondente for ^ (\d{7}) $, então $1 na regra de tradução representará os números discados de 7 dígitos.

   - Adicionais Digite um valor no campo **dígitos para adicionar** para especificar os dígitos a serem anexados ao número traduzido (por exemplo, + 1425).

     Por exemplo, se **a correspondência de padrão** contiver ^{7}(\d) $ como o padrão para números discados e **regra de tradução** contém + 1425 $1 como o padrão para os números de telefone e. 164, a regra normaliza o 5550100 para + 14255550100.

7. (Opcional) Se a regra de normalização resulta em um número de telefone interno à sua organização, selecione **Extensão interna**.

8. (Opcional) Insira um número para testar a regra de normalização e clique em **Ir**. Os resultados do teste são exibidos em **Inserir um número para testar**.

    > [!NOTE]
    > É possível salvar uma regra de normalização que ainda não passou no teste e reconfigurá-la posteriormente. Para obter detalhes, consulte  [Test Voice Routing](https://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx).

9. Clique em **OK** para salvar a regra de normalização.

10. Clique em **OK** para salvar o plano de discagem.

11. Na página **Plano de Discagem**, clique em **Confirmar** e clique em **Confirmar tudo**.

    > [!NOTE]
    > Sempre que criar ou alterar uma regra de normalização, você deve executar o comando **Confirmar todos** para publicar a alteração na configuração. Para obter detalhes, consulte [publicar alterações pendentes na configuração de roteamento de voz no Skype for Business](voice-route-config-changes.md) na documentação de operações.

### <a name="to-define-a-normalization-rule-manually"></a>Para definir uma regra de normalização manualmente

1. Abrir o painel de controle do Skype for Business Server

2. Adicionais Siga as etapas em [criar ou modificar um plano de discagem no Skype for Business Server](dial-plans.md).

3. Em **nova regra** de normalização ou **Editar regra**de normalização, digite um nome que descreva o padrão de número que está normalizado em **nome** (por exemplo, nomeie a normalização rule5DigitExtension).

4. (Opcional) No campo **Descrição**, digite uma descrição da regra de normalização (por exemplo, "Traduzir extensões de 5 dígitos").

5. Em **Compilar uma regra de normalização**, clique em **Editar**.

6. Digite o seguinte em **Digitar uma expressão regular**:

   - Em **Corresponder este padrão**, especifique o padrão que você deseja usar para coincidir com o número de telefone discado.

   - Em **Regra de conversão**, especifique um padrão para o formato dos números de telefone E.164 convertidos.

     Por exemplo, se você inserir ^ (\d{7}) $ em **coincidir este padrão** e + 1425 $1 na **regra de tradução**, a regra normalizará 5550100 para + 14255550100.

7. (Opcional) Se a regra de normalização resulta em um número de telefone interno à sua organização, selecione **Extensão interna**.

8. (Opcional) Insira um número para testar a regra de normalização e clique em **Ir**. Os resultados do teste são exibidos em **Inserir um número para testar**.

9. Clique em **OK** para salvar a regra de normalização.

10. Clique em **OK** para salvar o plano de discagem.

11. Na página **Plano de Discagem**, clique em **Confirmar** e clique em **Confirmar tudo**.

    > [!NOTE]
    > Sempre que criar ou alterar uma regra de normalização, você deve executar o comando **Confirmar todos** para publicar a alteração na configuração. Para obter detalhes, consulte [publicar alterações pendentes na configuração de roteamento de voz no Skype for Business](voice-route-config-changes.md) na documentação de operações.


