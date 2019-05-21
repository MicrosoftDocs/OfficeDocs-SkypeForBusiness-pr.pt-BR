---
title: Definindo regras de tradução no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: O Skype for Business Server Enterprise Voice roteia chamadas com base em números de telefone normalizados para o formato E. 164. Isso significa que todas as cadeias de caracteres discadas devem ser normalizadas para o formato E. 164 para realizar a pesquisa de número reverso (RNL) para que elas possam ser traduzidas para o URI SIP correspondente. O Skype for Business Server oferece a capacidade de manipular a identificação chamada e a apresentação de identificação de chamadas.
ms.openlocfilehash: 633b0c16fefb66d1ea44f96b5f32c2ca91f357f2
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274972"
---
# <a name="defining-translation-rules-in-skype-for-business-server"></a>Definindo regras de tradução no Skype for Business Server

O Skype for Business Server Enterprise Voice roteia chamadas com base em números de telefone normalizados para o formato E. 164. Isso significa que todas as cadeias de caracteres discadas devem ser normalizadas para o formato E. 164 para realizar a pesquisa de número reverso (RNL) para que elas possam ser traduzidas para o URI SIP correspondente. O Skype for Business Server oferece a capacidade de manipular a identificação chamada e a apresentação de identificação de chamadas.

Com o Skype for Business Server, o número de telefone da pessoa chamada (ou seja, o número de telefone chamado) pode ser traduzido do formato E. 164 para o formato de discagem local necessário para o par de troncos (ou seja, o gateway associado, a troca de ramificação privada (PBX) ou o SIP tronco). Para fazer isso, você deve definir uma ou mais regras de conversão para converter a URI de Solicitação antes de roteá-la para o ponto de tronco.

## <a name="caller-id-presentation"></a>Apresentação da identificação de chamadas

O Skype for Business Server oferece a opção de também converter o número de telefone da pessoa que está chamando (ou seja, o número de telefone que o chamador está chamando) do formato E. 164 para o formato de discagem local necessário para o par de tronco. Por exemplo, é possível criar uma regra de conversão para remover o prefixo +44 do início de uma cadeia de caracteres de discagem e substituí-lo por 0144.

**Para configurar o recurso de identificação de chamadas usando o painel de controle do Skype for Business Server**

1. Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como um membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Para obter detalhes, consulte [delegar permissões de configuração](https://technet.microsoft.com/en-us/library/gg412735(v=ocs.15).aspx).
2. Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Skype for Business, confira [instalar e abrir ferramentas administrativas](../../management-tools/install-and-open-administrative-tools.md).
3. Na barra de navegação à esquerda, clique em **Roteamento de Voz** e depois, em **Configuração do Tronco**.
4. Na página Configuração do Tronco, clique duas vezes no tronco existente (por exemplo, o tronco **Global**) para exibir a caixa de diálogo **Editar Configuração do Tronco**.
5. Para configurar a apresentação da ID de chamadas:
    - Para escolher uma ou mais regras de uma lista de todas as regras de tradução disponíveis na sua implantação do Enterprise Voice, clique em **selecionar**. Em **Regras de Conversão de Número de Chamada**, clique nas regras que você deseja associar ao tronco e clique em **OK**.
    - Para definir uma nova regra de conversão e associá-la ao tronco, clique em **Novo**. 
    - Para editar uma regra de conversão que já esteja associada ao tronco, clique no nome da regra e clique em **Exibir detalhes**.
    - Para copiar uma regra de tradução existente para usar como ponto de partida para definir uma nova regra, clique no nome da regra, clique em **copiar**e, em seguida, clique em **colar**.
    - Para remover uma regra de conversão do tronco, destaque o nome da regra e clique em **Remover**.

> [!Warning] 
> Não associe regras de conversão a um tronco se não houver regras de conversão configuradas no ponto do tronco associado porque as duas regras podem entrar em conflito. 

## <a name="called-id-presentation"></a>Apresentação de ID chamada

> [!Important]
> A capacidade de associar uma ou mais regras de tradução a uma configuração de tronco Enterprise Voice deve ser usada como uma *alternativa* para configurar regras de tradução no par de troncos. Não associe as regras de tradução a uma configuração de tronco do Enterprise Voice se você tiver configurado regras de tradução no par de tronco porque as duas regras podem entrar em conflito. 

Você pode usar qualquer um dos seguintes métodos para criar ou modificar uma regra de Tradução:

- [Use a ferramenta criar uma regra de tradução](#create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool) para especificar valores para os dígitos iniciais, comprimento, dígitos a serem removidos e dígitos a serem adicionados e deixe o painel de controle do Skype for Business Server gerar o padrão correspondente e a regra de tradução para você.
- [Grave expressões regulares manualmente](#create-or-modify-a-translation-rule-manually) para definir o padrão correspondente e a regra de tradução.

> [!Note]
> Para obter informações sobre como escrever expressões regulares, consulte [expressões regulares do .NET Framework](http://go.microsoft.com/fwlink/p/?linkId=140927). 

### <a name="create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool"></a>Criar ou modificar uma regra de tradução usando a ferramenta criar regra de tradução

Siga estas etapas se quiser definir uma regra de tradução inserindo um conjunto de valores na ferramenta criar regra de tradução e habilitando o painel de controle do Skype for Business Server para gerar o padrão correspondente e a regra de tradução para você. 

**Para definir uma regra usando a ferramenta Compilar uma Regra de Conversão**

1. Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como um membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Para obter detalhes, consulte [delegar permissões de configuração](https://technet.microsoft.com/en-us/library/gg412735(v=ocs.15).aspx).
2. Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Skype for Business, confira [instalar e abrir ferramentas administrativas](../../management-tools/install-and-open-administrative-tools.md).
3. Para começar a definir uma regra de tradução, siga as etapas em [configurar um tronco com bypass de mídia](GET LINK AFTER MIGRATION)até a etapa 10 ou [configurar um tronco sem bypass de mídia](GET LINK AFTER MIGRATION) até a etapa 9.
4. Em  **Nome** na página  **Nova Regra de Conversão** ou **Editar Regra de Conversão**, digite um nome que descreve o padrão numérico que está convertido.
5. Adicionais Em **Descrição**, digite uma descrição da regra de tradução, por exemplo, a discagem de **longa distância internacional dos EUA**.
6. Na seção  **Compilar uma Regra de Conversão** da caixa de diálogo, insira valores nos seguintes campos:
    - **Dígitos iniciais**: (Opcional) especifique os dígitos iniciais dos números com os quais você deseja que o padrão corresponda. Por exemplo, digite  + nesse campo para corresponder os números no formato E.164 (que começa com +).
    - **Comprimento**: especifique o número de dígitos no padrão de correspondência e selecione se deseja que o padrão corresponda a números exatamente com esse comprimento, com um comprimento menor ou qualquer comprimento. Por exemplo, digite  **11** e selecione  **At least** na lista suspensa para fazer a correspondência de números com no mínimo 11 dígitos de comprimento.
    - **Dígitos a serem removidos**: (Opcional) especifique o número de dígitos iniciais a serem removidos. Por exemplo, digite **1** para retirar o + do início do número.
    - **Dígitos a adicionar**: (Opcional) especifique os dígitos a serem anexados aos números convertidos. Por exemplo, digite  **011** se quiser que 011 seja anexado aos números convertidos quando a regra for aplicada.
    
    Os valores inseridos nesses campos são refletidos no **padrão para coincidir e fazer** a **conversão** dos campos de regra. Por exemplo, se você especificar os valores de exemplo anterior, a expressão regular resultante no campo **padrão para matc**h será:
    
    **^\+(\d{9}\d +) $** 

    O campo  **Regra de conversão** especifica um padrão para o formato de números convertidos. Esse padrão tem duas partes:
    - Um valor (por exemplo, **$1**) que representa o número de dígitos no padrão de correspondência
    - Adicionais Um valor que você pode preceder inserindo-o no campo **dígitos para adicionar**

    Usando os valores de exemplo anteriores, **011 $1** é exibido no campo **regra de tradução** .
    
    Quando essa regra de tradução é aplicada, + 441235551010 se torna 011441235551010.
7. Clique em **OK** para salvar a regra de tradução.
8. Clique em **OK** para salvar a configuração do tronco.
9. Na página **tronco configuratio**n, clique em **confirmar**e, em seguida, clique em **confirmar tudo**. 

> [!Note]
> Sempre que você cria ou modifica uma regra de tradução, deve executar o comando **Commit All** para publicar a alteração de configuração. Para obter detalhes, consulte [publicar alterações pendentes na configuração de roteamento de voz](https://technet.microsoft.com/en-us/library/gg413088(v=ocs.15).aspx). 

### <a name="create-or-modify-a-translation-rule-manually"></a>Criar ou modificar manualmente uma regra de tradução

Siga estas etapas se quiser definir uma regra de tradução escrevendo uma expressão regular para o padrão correspondente e regra de tradução. 

**Para definir uma regra de tradução manualmente**

1. Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como um membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Para obter detalhes, consulte [delegar permissões de configuração](https://technet.microsoft.com/en-us/library/gg412735(v=ocs.15).aspx).
2. Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Skype for Business, confira [instalar e abrir ferramentas administrativas](../../management-tools/install-and-open-administrative-tools.md).
3. Para começar a definir uma regra de tradução, siga as etapas em [configurar um tronco com bypass de mídia](GET LINK AFTER MIGRATION)até a etapa 10 ou [configurar um tronco sem bypass de mídia](GET LINK AFTER MIGRATION) até a etapa 9.
4. No campo **nome** da página **nova regra de tradução** ou **Editar regra de tradução** , digite um nome que descreva o padrão de número que está sendo traduzido.
5. Adicionais Em **Descrição**, digite uma descrição da regra de tradução; por exemplo, a discagem de **longa distância internacional dos EUA**.
6. Clique em **Editar** na parte inferior da seção **construir uma regra de tradução** .
7. Digite o seguinte em digite uma **expressão regular**:
    - Em **coincidir com esse padrão**, especifique o padrão que será usado para corresponder os números a serem traduzidos.
    - Em **regra de tradução**, especifique um padrão para o formato dos números traduzidos.

    Por exemplo, se você inserir ** ^ \+(\d{9}\d +) $** em **coincidir este padrão** e **011 $1** na **regra de tradução**, a regra irá traduzir + 441235551010 para 011441235551010.
8. Clique em **OK** para salvar a regra de tradução.
9. Clique em **OK** para salvar a configuração do tronco.
10. Na página **Configuração do Tronco**, clique em **Confirmar** e clique em **Confirmar tudo**. 

> [!Note] 
> Sempre que você cria ou modifica uma regra de tradução, deve executar o comando **Commit All** para publicar a alteração de configuração. Para obter detalhes, consulte [publicar alterações pendentes na configuração de roteamento de voz](https://technet.microsoft.com/en-us/library/gg413088(v=ocs.15).aspx). 
