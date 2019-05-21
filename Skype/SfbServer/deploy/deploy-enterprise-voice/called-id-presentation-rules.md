---
title: Criar ou modificar uma regra de tradução para a apresentação de ID chamada no Skype for Business Server
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
ms.assetid: ba112df8-3bb4-48e4-a353-4bf9110ccd71
description: 'Resumo: saiba como definir uma regra de tradução usando a ferramenta criar regra de tradução no Skype for Business Server.'
ms.openlocfilehash: 13e89fd836c971085a3a1fc40b7e60793e10eb68
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275868"
---
# <a name="create-or-modify-a-translation-rule-for-called-id-presentation-in-skype-for-business-server"></a>Criar ou modificar uma regra de tradução para a apresentação de ID chamada no Skype for Business Server

**Resumo:** Saiba como definir uma regra de tradução usando a ferramenta criar regra de tradução no Skype for Business Server.

Siga estas etapas se quiser definir uma regra de tradução inserindo um conjunto de valores na ferramenta **criar regra de tradução** e habilitando o painel de controle do Skype for Business Server para gerar o padrão correspondente e a regra de tradução para você. Se preferir, é possível gravar uma expressão regular manualmente para definir o padrão de correspondência e a regra de conversão. Para obter detalhes, consulte [Create or Modify a Translation Rule Manually](https://technet.microsoft.com/library/049d1db3-af58-48c5-be89-52e1d068a4bd.aspx).

### <a name="to-define-a-rule-by-using-the-build-a-translation-rule-tool"></a>Para definir uma regra usando a ferramenta Compilar uma Regra de Conversão

1. Abra o painel de controle do Skype for Business Server.

2. Para começar a definir uma regra de tradução, siga as etapas em [configurar um tronco com bypass de mídia no Skype for Business Server](configure-trunk-with-media-bypass.md) por meio da etapa 10 ou [Configure um tronco sem bypass de mídia no Skype for Business Server](configure-trunk-without-media-bypass.md) até a etapa 9.

3. Em  **Nome** na página  **Nova Regra de Conversão** ou **Editar Regra de Conversão**, digite um nome que descreve o padrão numérico que está convertido.

4. Adicionais Em **Descrição**, digite uma descrição da regra de tradução, por exemplo, para a discagem de longa distância internacional dos EUA.

5. Na seção  **Compilar uma Regra de Conversão** da caixa de diálogo, insira valores nos seguintes campos:

   - **Dígitos iniciais**: (Opcional) especifique os dígitos iniciais dos números com os quais você deseja que o padrão corresponda. Por exemplo, digite  + nesse campo para corresponder os números no formato E.164 (que começa com +).

   - **Comprimento**: especifique o número de dígitos no padrão de correspondência e selecione se deseja que o padrão corresponda a números exatamente com esse comprimento, com um comprimento menor ou qualquer comprimento. Por exemplo, digite 11 e selectAt menos na lista suspensa para corresponder a números com pelo menos 11 dígitos de comprimento.

   - **Dígitos a serem removidos**: (Opcional) especifique o número de dígitos iniciais a serem removidos. Por exemplo, insira 1 para dividir o + do início do número.

   - **Dígitos a adicionar**: (Opcional) especifique os dígitos a serem anexados aos números convertidos. Por exemplo, digite  011 se quiser que 011 seja anexado aos números convertidos quando a regra for aplicada.

     Os valores inseridos nesses campos são refletidos nos campos  **Padrão a ser correspondido** e  **Regra de conversão**. Por exemplo, se você especificar os valores do exemplo anterior, a expressão regular resultante no campo  **Padrão a ser correspondido** será:

     ^\+(\d{9}\d +) $

     O campo  **Regra de conversão** especifica um padrão para o formato de números convertidos. Esse padrão tem duas partes:

   - Um valor (por exemplo, $1) que representa o número de dígitos no padrão de correspondência

   - Adicionais Um valor que você pode preceder inserindo-o no campo **dígitos para adicionar**

     Usando os valores de exemplo anteriores, 011 $1 é exibido no campo **regra de tradução** .

     Quando essa regra de tradução é aplicada, + 441235551010 se torna 011441235551010.

6. Clique em **OK** para salvar a regra de tradução.

7. Clique em **OK** para salvar a configuração do tronco.

8. Na página **Configuração do Tronco**, clique em **Confirmar** e clique em **Confirmar tudo**.

   > [!NOTE]
   > Sempre que você cria ou modifica uma regra de tradução, deve executar o comando **Commit All** para publicar a alteração de configuração. Para obter detalhes, consulte [publicar alterações pendentes na configuração de roteamento de voz no Skype for Business](voice-route-config-changes.md) na documentação de operações.

### <a name="to-define-a-translation-rule-manually"></a>Para definir uma regra de tradução manualmente

1. Abrir o painel de controle do Skype for Business Server

2. Para começar a definir uma regra de tradução, siga as etapas em [configurar um tronco com bypass de mídia no Skype for Business Server](configure-trunk-with-media-bypass.md) por meio da etapa 10 ou [Configure um tronco sem bypass de mídia no Skype for Business Server](configure-trunk-without-media-bypass.md) até a etapa 9.

3. No campo **nome** da página **nova regra de tradução** ou **Editar regra de tradução** , digite um nome que descreva o padrão de número que está sendo traduzido.

4. Adicionais Em **Descrição**, digite uma descrição da regra de tradução, por exemplo, para a discagem de longa distância internacional dos EUA.

5. Clique em **Editar** na parte inferior da seção **construir uma regra de tradução** .

6. Digite o seguinte em **Digitar uma expressão regular**:

   - Em **coincidir com esse padrão**, especifique o padrão que será usado para corresponder os números a serem traduzidos.

   - Em **regra de tradução**, especifique um padrão para o formato dos números traduzidos.

     Por exemplo, se você inserir ^\+(\d{9}\d +) $ em **correspondência a este padrão** And011 $1 na **regra de tradução**, a regra irá traduzir + 441235551010 para 011441235551010.

7. Clique em **OK** para salvar a regra de tradução.

8. Clique em **OK** para salvar a configuração do tronco.

9. Na página **Configuração do Tronco**, clique em **Confirmar** e clique em **Confirmar tudo**.

    > [!NOTE]
    > Sempre que você cria ou modifica uma regra de tradução, deve executar o comando **Commit All** para publicar a alteração de configuração. Para obter detalhes, consulte [publicar alterações pendentes na configuração de roteamento de voz no Skype for Business](voice-route-config-changes.md) na documentação de operações.

## <a name="see-also"></a>Confira também

[Configurar um tronco com bypass de mídia no Skype for Business Server](configure-trunk-with-media-bypass.md)

[Configurar um tronco sem bypass de mídia no Skype for Business Server](configure-trunk-without-media-bypass.md)

[Publicar alterações pendentes na configuração de roteamento de voz no Skype for Business](voice-route-config-changes.md)

[Implantar bypass de mídia no Skype for Business Server](deploy-media-bypass.md)

