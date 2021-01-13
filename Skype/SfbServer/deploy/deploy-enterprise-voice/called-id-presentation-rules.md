---
title: Criar ou modificar uma regra de conversão para apresentação de ID chamada no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ba112df8-3bb4-48e4-a353-4bf9110ccd71
description: 'Resumo: Saiba como definir uma regra de conversão usando a ferramenta Criar uma Regra de Conversão no Skype for Business Server.'
ms.openlocfilehash: b93d271abd0ade1b178e859f2a0599464a6759e5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804191"
---
# <a name="create-or-modify-a-translation-rule-for-called-id-presentation-in-skype-for-business-server"></a>Criar ou modificar uma regra de conversão para apresentação de ID chamada no Skype for Business Server

**Resumo:** Saiba como definir uma regra de conversão usando a ferramenta Criar uma Regra de Conversão no Skype for Business Server.

Siga estas etapas se quiser definir uma regra de conversão inserindo um conjunto de valores na ferramenta **Criar** uma Regra de Conversão e habilitando o Painel de Controle do Skype for Business Server para gerar o padrão de correspondência correspondente e a regra de conversão para você. Se preferir, é possível gravar uma expressão regular manualmente para definir o padrão de correspondência e a regra de conversão. Para obter detalhes, consulte [Create or Modify a Translation Rule Manually](https://technet.microsoft.com/library/049d1db3-af58-48c5-be89-52e1d068a4bd.aspx).

### <a name="to-define-a-rule-by-using-the-build-a-translation-rule-tool"></a>Para definir uma regra usando a ferramenta Compilar uma Regra de Conversão

1. Abra o Painel de Controle do Skype for Business Server.

2. Para começar a definir uma regra de conversão, siga as etapas em Configurar um tronco com bypass de mídia no [Skype for Business Server](configure-trunk-with-media-bypass.md) até a etapa 10 ou Configurar um tronco sem bypass de mídia no Skype for Business Server até [a](configure-trunk-without-media-bypass.md) etapa 9.

3. Em **Nome** na página **Nova Regra de Conversão** ou **Editar Regra de Conversão**, digite um nome que descreve o padrão numérico que está convertido.

4. (Opcional) Em **Descrição,** digite uma descrição da regra de conversão, por exemplo, discagem de longa distância internacional dos EUA.

5. Na seção **Compilar uma Regra de Conversão** da caixa de diálogo, insira valores nos seguintes campos:

   - **Dígitos iniciais**: (Opcional) especifique os dígitos iniciais dos números com os quais você deseja que o padrão corresponda. Por exemplo, digite + nesse campo para corresponder os números no formato E.164 (que começa com +).

   - **Comprimento**: especifique o número de dígitos no padrão de correspondência e selecione se deseja que o padrão corresponda a números exatamente com esse comprimento, com um comprimento menor ou qualquer comprimento. Por exemplo, digite 11 e selecioneNo mínimo na lista de lista lista para corresponder aos números que têm pelo menos 11 dígitos de comprimento.

   - **Dígitos a serem removidos**: (Opcional) especifique o número de dígitos iniciais a serem removidos. Por exemplo, digite 1 para retirar o+ do início do número.

   - **Dígitos a adicionar**: (Opcional) especifique os dígitos a serem anexados aos números convertidos. Por exemplo, digite 011 se quiser que 011 seja anexado aos números convertidos quando a regra é aplicada.

     Os valores inseridos nesses campos são refletidos nos campos **Padrão a ser correspondido** e **Regra de conversão**. Por exemplo, se você especificar os valores do exemplo anterior, a expressão regular resultante no campo **Padrão a ser correspondido** será:

     ^\+(\d {9} \d+)$

     O campo **Regra de conversão** especifica um padrão para o formato de números convertidos. Esse padrão tem duas partes:

   - Um valor (por exemplo, $1) que representa o número de dígitos no padrão correspondido

   - (Opcional) Um valor que pode ser anexado digitando no campo **Dígitos a adicionar**

     Usando os valores do exemplo anterior, 011$1 aparece no campo **Regra de conversão**.

     Quando essa regra de conversão é aplicada, +441235551010 se torna 011441235551010.

6. Clique em **OK** para salvar a regra de tradução.

7. Clique em **OK** para salvar a configuração de tronco.

8. Na página **Configuração do Tronco**, clique em **Confirmar** e clique em **Confirmar tudo**.

   > [!NOTE]
   > Sempre que criar ou modificar uma regra de tradução, será necessário executar o comando **Confirmar tudo** para publicar a alteração de configuração. Para obter detalhes, [consulte Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.

### <a name="to-define-a-translation-rule-manually"></a>Como definir uma regra de conversão manualmente

1. Abrir o Painel de Controle do Skype for Business Server

2. Para começar a definir uma regra de conversão, siga as etapas em Configurar um tronco com bypass de mídia no [Skype for Business Server](configure-trunk-with-media-bypass.md) até a etapa 10 ou Configurar um tronco sem bypass de mídia no Skype for Business Server até [a](configure-trunk-without-media-bypass.md) etapa 9.

3. No campo **Nome**, na página **Nova Regra de Conversão** ou **Editar Regra de Conversão**, digite um nome que descreva o padrão de número sendo convertido.

4. (Opcional) Em **Descrição,** digite uma descrição da regra de conversão, por exemplo, discagem de longa distância internacional dos EUA.

5. Clique em **Editar** na parte inferior da seção **Criar uma Regra de Conversão**.

6. Insira no campo **Digite uma Expressão Regular** o seguinte:

   - No campo **Corresponder a este padrão**, especifique o padrão que será usado para corresponder os números a serem convertidos.

   - No campo **Regra de conversão**, especifique o padrão para o formato dos números convertidos.

     Por exemplo, se você inserir ^ (\d \d+)$ em Corresponder este padrão e011$1 na regra de conversão , a regra traduzirá \+ {9} +441235551010 para 011441235551010.  

7. Clique em **OK** para salvar a regra de tradução.

8. Clique em **OK** para salvar a configuração de tronco.

9. Na página **Configuração do Tronco**, clique em **Confirmar** e clique em **Confirmar tudo**.

    > [!NOTE]
    > Sempre que criar ou modificar uma regra de tradução, será necessário executar o comando **Confirmar tudo** para publicar a alteração de configuração. Para obter detalhes, [consulte Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.

## <a name="see-also"></a>Confira também

[Configurar um tronco com bypass de mídia no Skype for Business Server](configure-trunk-with-media-bypass.md)

[Configurar um tronco sem bypass de mídia no Skype for Business Server](configure-trunk-without-media-bypass.md)

[Publicar alterações pendentes na configuração de roteamento de voz no Skype for Business](voice-route-config-changes.md)

[Implantar bypass de mídia no Skype for Business Server](deploy-media-bypass.md)

