---
title: Criar ou modificar uma regra de conversão para a apresentação chamada de ID no Skype for Business Server
ms.reviewer: null
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
ms.custom: null
ms.assetid: ba112df8-3bb4-48e4-a353-4bf9110ccd71
description: 'Resumo: saiba como definir uma regra de conversão usando a ferramenta Criar uma regra de conversão em Skype for Business Server.'
---

# <a name="create-or-modify-a-translation-rule-for-called-id-presentation-in-skype-for-business-server"></a>Criar ou modificar uma regra de conversão para a apresentação chamada de ID no Skype for Business Server

**Resumo:** Saiba como definir uma regra de conversão usando a ferramenta Criar uma Regra de Conversão Skype for Business Server.

Siga estas etapas se quiser definir uma regra de conversão inserindo um conjunto de valores na ferramenta **Criar** uma Regra de Conversão e habilitando o Painel de Controle Skype for Business Server a gerar o padrão correspondente e a regra de conversão para você. Se preferir, é possível gravar uma expressão regular manualmente para definir o padrão de correspondência e a regra de conversão. Para obter detalhes, consulte [Create or Modify a Translation Rule Manually](/previous-versions/office/lync-server-2013/lync-server-2013-create-or-modify-a-translation-rule-manually).

### <a name="to-define-a-rule-by-using-the-build-a-translation-rule-tool"></a>Para definir uma regra usando a ferramenta Compilar uma Regra de Conversão

1. Abra Skype for Business Server Painel de Controle.

2. Para começar a definir uma regra de conversão, siga as etapas em [Configure a trunk with media bypass in Skype for Business Server](configure-trunk-with-media-bypass.md) through step 10 ou [Configure a trunk without media bypass in Skype for Business Server](configure-trunk-without-media-bypass.md) through step 9.

3. Em **Nome** na página **Nova Regra de Conversão** ou **Editar Regra de Conversão**, digite um nome que descreve o padrão numérico que está convertido.

4. (Opcional) Em **Descrição**, digite uma descrição da regra de conversão, por exemplo, discagem de longa distância internacional dos EUA.

5. Na seção **Compilar uma Regra de Conversão** da caixa de diálogo, insira valores nos seguintes campos:

   - **Dígitos iniciais**: (Opcional) especifique os dígitos iniciais dos números com os quais você deseja que o padrão corresponda. Por exemplo, digite + nesse campo para corresponder os números no formato E.164 (que começa com +).

   - **Comprimento**: especifique o número de dígitos no padrão de correspondência e selecione se deseja que o padrão corresponda a números exatamente com esse comprimento, com um comprimento menor ou qualquer comprimento. Por exemplo, insira 11 e selecioneNo mínimo na listada para corresponder a números que têm pelo menos 11 dígitos de comprimento.

   - **Dígitos a serem removidos**: (Opcional) especifique o número de dígitos iniciais a serem removidos. Por exemplo, digite 1 para retirar o+ do início do número.

   - **Dígitos a adicionar**: (Opcional) especifique os dígitos a serem anexados aos números convertidos. Por exemplo, digite 011 se quiser que 011 seja anexado aos números convertidos quando a regra é aplicada.

     Os valores inseridos nesses campos são refletidos nos campos **Padrão a ser correspondido** e **Regra de conversão**. Por exemplo, se você especificar os valores do exemplo anterior, a expressão regular resultante no campo **Padrão a ser correspondido** será:

     ^\+(\d{9}\d+)$

     O campo **Regra de conversão** especifica um padrão para o formato de números convertidos. Esse padrão tem duas partes:

   - Um valor (por exemplo, $1) que representa o número de dígitos no padrão correspondido

   - (Opcional) Um valor que pode ser anexado digitando no campo **Dígitos a adicionar**

     Usando os valores do exemplo anterior, 011$1 aparece no campo **Regra de conversão**.

     Quando essa regra de conversão é aplicada, +441235551010 se torna 011441235551010.

6. Clique em **OK** para salvar a regra de tradução.

7. Clique em **OK** para salvar a configuração de tronco.

8. Na página **Configuração do Tronco**, clique em **Confirmar** e clique em **Confirmar tudo**.

   > [!NOTE]
   > Sempre que criar ou modificar uma regra de tradução, será necessário executar o comando **Confirmar tudo** para publicar a alteração de configuração. Para obter detalhes, [consulte Publicar alterações pendentes na](voice-route-config-changes.md) configuração de roteamento de voz Skype for Business na documentação Operações.

### <a name="to-define-a-translation-rule-manually"></a>Como definir uma regra de conversão manualmente

1. Abrir Skype for Business Server Painel de Controle

2. Para começar a definir uma regra de conversão, siga as etapas em [Configure a trunk with media bypass in Skype for Business Server](configure-trunk-with-media-bypass.md) through step 10 ou [Configure a trunk without media bypass in Skype for Business Server](configure-trunk-without-media-bypass.md) through step 9.

3. No campo **Nome**, na página **Nova Regra de Conversão** ou **Editar Regra de Conversão**, digite um nome que descreva o padrão de número sendo convertido.

4. (Opcional) Em **Descrição**, digite uma descrição da regra de conversão, por exemplo, discagem de longa distância internacional dos EUA.

5. Clique em **Editar** na parte inferior da seção **Criar uma Regra de Conversão**.

6. Insira no campo **Digite uma Expressão Regular** o seguinte:

   - No campo **Corresponder a este padrão**, especifique o padrão que será usado para corresponder os números a serem convertidos.

   - No campo **Regra de conversão**, especifique o padrão para o formato dos números convertidos.

     Por exemplo, se você inserir ^\+(\d\d{9}+)$ em Corresponder a esse padrão e011$**1 na regra** de conversão, a regra traduzirá +441235551010 para 011441235551010.

7. Clique em **OK** para salvar a regra de tradução.

8. Clique em **OK** para salvar a configuração de tronco.

9. Na página **Configuração do Tronco**, clique em **Confirmar** e clique em **Confirmar tudo**.

    > [!NOTE]
    > Sempre que criar ou modificar uma regra de tradução, será necessário executar o comando **Confirmar tudo** para publicar a alteração de configuração. Para obter detalhes, [consulte Publicar alterações pendentes na](voice-route-config-changes.md) configuração de roteamento de voz Skype for Business na documentação Operações.

## <a name="see-also"></a>Confira também

[Configurar um tronco com bypass de mídia Skype for Business Server](configure-trunk-with-media-bypass.md)

[Configurar um tronco sem bypass de mídia Skype for Business Server](configure-trunk-without-media-bypass.md)

[Publicar alterações pendentes na configuração de roteamento de voz Skype for Business](voice-route-config-changes.md)

[Implantar bypass de mídia Skype for Business Server](deploy-media-bypass.md)