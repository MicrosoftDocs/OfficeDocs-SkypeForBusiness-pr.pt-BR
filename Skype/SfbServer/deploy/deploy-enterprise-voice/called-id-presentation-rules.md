---
title: Criar ou modificar uma regra de conversão para apresentação da ID chamada no Skype para Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ba112df8-3bb4-48e4-a353-4bf9110ccd71
description: 'Resumo: Saiba como definir uma regra de conversão usando a compilar uma ferramenta de regra de conversão no Skype para Business Server.'
ms.openlocfilehash: 1d1d8fff6c4ab114c2c12d71ec52017d5c491bef
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23886258"
---
# <a name="create-or-modify-a-translation-rule-for-called-id-presentation-in-skype-for-business-server"></a>Criar ou modificar uma regra de conversão para apresentação da ID chamada no Skype para Business Server

**Resumo:** Saiba como definir uma regra de conversão usando a compilar uma ferramenta de regra de conversão no Skype para Business Server.

Se você deseja definir uma regra de conversão digitando um conjunto de valores na ferramenta **compilar uma regra de conversão** e habilitando Skype para painel de controle do Business Server gerar o padrão de correspondência correspondente e uma regra de conversão para você, siga estas etapas. Se preferir, é possível gravar uma expressão regular manualmente para definir o padrão de correspondência e a regra de conversão. Para obter detalhes, consulte [criar ou modificar uma regra de conversão manualmente](https://technet.microsoft.com/library/049d1db3-af58-48c5-be89-52e1d068a4bd.aspx).

### <a name="to-define-a-rule-by-using-the-build-a-translation-rule-tool"></a>Para definir uma regra usando a ferramenta Compilar uma Regra de Conversão

1. Abra o Skype para painel de controle do servidor de negócios.

2. Para começar a definir uma regra de conversão, siga as etapas em [Configure um tronco com mídia ignorar no Skype para Business Server](configure-trunk-with-media-bypass.md) por meio da etapa 10 ou [Configure um tronco sem media bypass no Skype para Business Server](configure-trunk-without-media-bypass.md) até a etapa 9.

3. Em  **Nome** na página  **Nova Regra de Conversão** ou **Editar Regra de Conversão**, digite um nome que descreve o padrão numérico que está convertido.

4. (Opcional) Em **Descrição**, digite uma descrição da regra de conversão, por exemplo US internacional de longa distância.

5. Na seção  **Compilar uma Regra de Conversão** da caixa de diálogo, insira valores nos seguintes campos:

   - **Dígitos iniciais**: (Opcional) especifique os dígitos iniciais dos números com os quais você deseja que o padrão corresponda. Por exemplo, digite  + nesse campo para corresponder os números no formato E.164 (que começa com +).

   - **Comprimento**: especifique o número de dígitos no padrão de correspondência e selecione se deseja que o padrão corresponda a números exatamente com esse comprimento, com um comprimento menor ou qualquer comprimento. Por exemplo, insira 11 e selectAt mínimos na lista suspensa para corresponder os números que estão pelo menos 11 dígitos de comprimento.

   - **Dígitos a serem removidos**: (Opcional) especifique o número de dígitos iniciais a serem removidos. Por exemplo, digite 1 para retirar a + desde o início do número.

   - **Dígitos a adicionar**: (Opcional) especifique os dígitos a serem anexados aos números convertidos. Por exemplo, digite  011 se quiser que 011 seja anexado aos números convertidos quando a regra for aplicada.

    Os valores inseridos nesses campos são refletidos nos campos  **Padrão a ser correspondido** e  **Regra de conversão**. Por exemplo, se você especificar os valores do exemplo anterior, a expressão regular resultante no campo  **Padrão a ser correspondido** será:

    ^\+(\d{9}\d+)$

    O campo  **Regra de conversão** especifica um padrão para o formato de números convertidos. Esse padrão tem duas partes:

   - Um valor (por exemplo, $1) que representa o número de dígitos no padrão correspondido

   - (Opcional) Um valor que pode ser anexado digitando no campo **Dígitos a adicionar**

    Usando os valores do exemplo anterior, 011$1 aparece no campo **Regra de conversão**.

    Quando essa regra de conversão é aplicada, +441235551010 se torna 011441235551010.

6. Clique em **OK** para salvar a regra de tradução.

7. Clique em  **OK** para salvar a configuração de tronco.

8. Na página **Configuração do Tronco**, clique em **Confirmar** e clique em **Confirmar tudo**.

   > [!NOTE]
   > Sempre que criar ou modificar uma regra de conversão, será necessário executar o comando **Confirmar tudo** para publicar a alteração de configuração. Para obter detalhes, consulte [Publish alterações pendentes para a configuração de roteamento de voz no Skype para negócios](voice-route-config-changes.md) na documentação operações.

### <a name="to-define-a-translation-rule-manually"></a>Como definir uma regra de conversão manualmente

1. Abra o Skype para painel de controle do servidor de negócios

2. Para começar a definir uma regra de conversão, siga as etapas em [Configure um tronco com mídia ignorar no Skype para Business Server](configure-trunk-with-media-bypass.md) por meio da etapa 10 ou [Configure um tronco sem media bypass no Skype para Business Server](configure-trunk-without-media-bypass.md) até a etapa 9.

3. No campo **Nome**, na página **Nova Regra de Conversão** ou **Editar Regra de Conversão**, digite um nome que descreva o padrão de número sendo convertido.

4. (Opcional) Em **Descrição**, digite uma descrição da regra de conversão, por exemplo longa distância internacional EUA discando.

5. Clique em  **Editar** na parte inferior da seção  **Compilar uma Regra de Conversão**.

6. Digite o seguinte em  **Digitar uma expressão regular**:

   - No campo  **Corresponder a este padrão**, especifique o padrão que será usado para corresponder aos números a serem convertidos.

   - No campo  **Regra de conversão**, especifique o padrão para o formato dos números convertidos.

    Por exemplo, se você inserir ^\+(\d{9}\d+)$ em **corresponder este padrão** and011$ 1 em **regra de conversão**, a regra converterá + 441235551010 em 011441235551010.

7. Clique em  **OK** para salvar a regra de tradução.

8. Clique em  **OK** para salvar a configuração de tronco.

9. Na página **Configuração do Tronco**, clique em **Confirmar** e clique em **Confirmar tudo**.

    > [!NOTE]
    > Sempre que criar ou modificar uma regra de conversão, será necessário executar o comando **Confirmar tudo** para publicar a alteração de configuração. Para obter detalhes, consulte [Publish alterações pendentes para a configuração de roteamento de voz no Skype para negócios](voice-route-config-changes.md) na documentação operações.

## <a name="see-also"></a>Consulte também

[Configurar um tronco com bypass de mídia no Skype para Business Server](configure-trunk-with-media-bypass.md)

[Configurar um tronco sem bypass de mídia no Skype para Business Server](configure-trunk-without-media-bypass.md)

[Publicar alterações pendentes para a configuração de roteamento de voz no Skype para negócios](voice-route-config-changes.md)

[Implantar o bypass de mídia no Skype para Business Server](deploy-media-bypass.md)

