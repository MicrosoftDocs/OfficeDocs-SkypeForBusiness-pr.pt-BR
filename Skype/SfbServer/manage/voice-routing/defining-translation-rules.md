---
title: Definindo regras de conversão no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: O Skype for Business Server Enterprise Voice roteia chamadas com base em números de telefone normalizados para o formato E. 164. Isso significa que todas as cadeias de caracteres discadas devem ser normalizadas para o formato E. 164 para o propósito de executar a pesquisa de número reverso (RNL), de modo que eles possam ser convertidos em seu URI SIP correspondente. O Skype for Business Server oferece a capacidade de manipular a ID chamada e a apresentação da ID do chamador.
ms.openlocfilehash: 49598c2ef6b1a145c206bece3e06068067b0a0e0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151201"
---
# <a name="defining-translation-rules-in-skype-for-business-server"></a>Definindo regras de conversão no Skype for Business Server

O Skype for Business Server Enterprise Voice roteia chamadas com base em números de telefone normalizados para o formato E. 164. Isso significa que todas as cadeias de caracteres discadas devem ser normalizadas para o formato E. 164 para o propósito de executar a pesquisa de número reverso (RNL), de modo que eles possam ser convertidos em seu URI SIP correspondente. O Skype for Business Server oferece a capacidade de manipular a ID chamada e a apresentação da ID do chamador.

Com o Skype for Business Server, o número de telefone do participante chamado (ou seja, o número de telefone chamado) pode ser convertido no formato E. 164 para o formato de discagem local necessário para o par de tronco (ou seja, o gateway associado, o PBX (central privada de comutação telefônica) ou o SIP tronco). Para fazer isso, você deve definir uma ou mais regras de conversão para converter o URI de solicitação antes de roteá-lo para o par de tronco.

## <a name="caller-id-presentation"></a>Apresentação da ID do chamador

O Skype for Business Server oferece a opção de também converter o número de telefone da pessoa que está chamando (ou seja, o número de telefone que o chamador está chamando) do formato E. 164 para o formato de discagem local exigido pelo par de tronco. Por exemplo, você pode criar uma regra de conversão para remover +44 do começo de uma sequência de caracteres de discagem e o substituir por 0144.

**Para configurar a ID de chamadas usando o painel de controle do Skype for Business Server**

1. Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Para obter detalhes, consulte [delegar permissões de configuração](https://technet.microsoft.com/library/gg412735(v=ocs.15).aspx).
2. Abra uma janela do navegador e insira a URL do administrador para abrir o painel de controle. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Skype for Business, consulte [instalar e abrir ferramentas administrativas](../../management-tools/install-and-open-administrative-tools.md).
3. Na barra de navegação esquerda, clique em **Roteamento de Voz** e clique em **Configuração de Tronco**.
4. Na página configuração do tronco, clique duas vezes em um tronco existente (por exemplo, o tronco **global** ) para exibir a caixa de diálogo **Editar configuração do tronco** .
5. Para configurar a apresentação da ID de chamadas:
    - Para escolher uma ou mais regras de uma lista de todas as regras de conversão disponíveis em sua implantação do Enterprise Voice, clique em **selecionar**. Em **regras de conversão de número de chamada**, clique nas regras que você deseja associar ao tronco e, em seguida, clique em **OK**.
    - Para definir uma nova regra de conversão e associá-la ao tronco, clique em **Novo**. 
    - Para editar uma regra de conversão que já está associada ao tronco, clique no nome da regra e, depois, em **Mostrar detalhes**.
    - Para copiar uma regra de conversão existente para usar como um ponto de partida para definir uma nova regra, clique no nome da regra, clique em **copiar**e clique em **colar**.
    - Para remover uma regra de conversão do tronco, destaque o nome da regra e clique em **Remover **.

> [!Warning] 
> Não associe regras de conversão a um tronco se você tiver configurado as regras de conversão no ponto de tronco associado, pois as duas regras podem entrar em conflito. 

## <a name="called-id-presentation"></a>Apresentação da ID chamada

> [!Important]
> A capacidade de associar uma ou mais regras de conversão de uma configuração de tronco do Enterprise Voice se destina a ser usada como uma *alternativa * para configurar as regras de conversão no ponto de tronco. Não associe as regras de conversão de uma configuração de tronco Enterprise Voice se você tiver configurado regras de conversão no peer de tronco, porque as duas regras podem entrar em conflito. 

Você pode usar um dos seguintes métodos para compilar ou modificar uma regra de conversão:

- [Use a ferramenta criar uma regra de conversão](#create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool) para especificar valores para os dígitos iniciais, comprimento, dígitos a serem removidos e dígitos a serem adicionados e, em seguida, permita que o painel de controle do Skype for Business Server gere o padrão correspondente e a regra de conversão para você.
- [Escreva expressões regulares manualmente](#create-or-modify-a-translation-rule-manually) para definir o padrão de correspondência e a regra de conversão.

> [!Note]
> Para obter informações sobre como escrever expressões regulares, consulte [expressões regulares do .NET Framework](https://go.microsoft.com/fwlink/p/?linkId=140927). 

### <a name="create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool"></a>Criar ou modificar uma regra de conversão usando a ferramenta compilar uma regra de conversão

Siga estas etapas se você quiser definir uma regra de conversão inserindo um conjunto de valores na ferramenta criar uma regra de conversão e habilitando o painel de controle do Skype for Business Server para gerar o padrão correspondente e a regra de conversão para você. 

**Para definir uma regra usando a ferramenta Compilar uma Regra de Conversão**

1. Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Para obter detalhes, consulte [delegar permissões de configuração](https://technet.microsoft.com/library/gg412735(v=ocs.15).aspx).
2. Abra uma janela do navegador e insira a URL do administrador para abrir o painel de controle. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Skype for Business, consulte [instalar e abrir ferramentas administrativas](../../management-tools/install-and-open-administrative-tools.md).
3. Para começar a definir uma regra de conversão, siga as etapas em [configurar um tronco com bypass de mídia](GET LINK AFTER MIGRATION)até a etapa 10 ou [configurar um tronco sem bypass de mídia](GET LINK AFTER MIGRATION) até a etapa 9.
4. Em **Nome** na página **Nova Regra de Conversão** ou **Editar Regra de Conversão**, digite um nome que descreve o padrão numérico que está convertido.
5. Opcion Em **Descrição**, digite uma descrição da regra de conversão, por exemplo, **discagem de longa distância internacional dos EUA**.
6. Na seção **Compilar uma Regra de Conversão** da caixa de diálogo, insira valores nos seguintes campos:
    - **Dígitos iniciais**: (Opcional) especifique os dígitos iniciais dos números com os quais você deseja que o padrão corresponda. Por exemplo, digite + nesse campo para corresponder os números no formato E.164 (que começa com +).
    - **Comprimento**: especifique o número de dígitos no padrão de correspondência e selecione se deseja que o padrão corresponda a números exatamente com esse comprimento, com um comprimento menor ou qualquer comprimento. Por exemplo, digite **11** e selecione **No mínimo** na lista suspensa para fazer a correspondência de números com no mínimo 11 dígitos de comprimento.
    - **Dígitos a serem removidos**: (Opcional) especifique o número de dígitos iniciais a serem removidos. Por exemplo, digite **1** para retirar o + do início do número.
    - **Dígitos a adicionar**: (Opcional) especifique os dígitos a serem anexados aos números convertidos. Por exemplo, digite **011** se quiser que 011 seja anexado aos números convertidos quando a regra é aplicada.
    
    Os valores inseridos nesses campos são refletidos no **padrão para corresponder** e **conversão** de campos de regra. Por exemplo, se você especificar os valores de exemplo anteriores, a expressão regular resultante no campo **padrão para matc**h será:
    
    **^\+(\d{9}\d +) $** 

    O campo **Regra de conversão** especifica um padrão para o formato de números convertidos. Esse padrão tem duas partes:
    - Um valor (por exemplo, **$1**) que representa o número de dígitos no padrão correspondido
    - (Opcional) Um valor que pode ser anexado digitando no campo **Dígitos a adicionar**

    Usando os valores do exemplo anterior, **011$1** aparece no campo **Regra de conversão**.
    
    Quando essa regra de conversão é aplicada, +441235551010 se torna 011441235551010.
7. Clique em **OK** para salvar a regra de tradução.
8. Clique em **OK** para salvar a configuração de tronco.
9. Na página **tronco configuratio**n, clique em **confirmar**e em **confirmar tudo**. 

> [!Note]
> Sempre que criar ou modificar uma regra de tradução, será necessário executar o comando **Confirmar tudo** para publicar a alteração de configuração. Para obter detalhes, consulte [Publish Pending Changes to The Voice Routing Configuration](https://technet.microsoft.com/library/gg413088(v=ocs.15).aspx). 

### <a name="create-or-modify-a-translation-rule-manually"></a>Criar ou modificar uma regra de conversão manualmente

Siga estas etapas para definir uma regra de conversão desenvolvendo uma expressão regular para o padrão de correspondência e a regra de conversão. 

**Como definir uma regra de conversão manualmente**

1. Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Para obter detalhes, consulte [delegar permissões de configuração](https://technet.microsoft.com/library/gg412735(v=ocs.15).aspx).
2. Abra uma janela do navegador e insira a URL do administrador para abrir o painel de controle. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Skype for Business, consulte [instalar e abrir ferramentas administrativas](../../management-tools/install-and-open-administrative-tools.md).
3. Para começar a definir uma regra de conversão, siga as etapas em [configurar um tronco com bypass de mídia](GET LINK AFTER MIGRATION)até a etapa 10 ou [configurar um tronco sem bypass de mídia](GET LINK AFTER MIGRATION) até a etapa 9.
4. No campo **Nome**, na página **Nova Regra de Conversão** ou **Editar Regra de Conversão**, digite um nome que descreva o padrão de número sendo convertido.
5. Opcion Em **Descrição**, digite uma descrição da regra de conversão; por exemplo, **discagem interurbana internacional**.
6. Clique em **Editar** na parte inferior da seção **Criar uma Regra de Conversão**.
7. Digite o seguinte em digitar uma **expressão regular**:
    - No campo **Corresponder a este padrão**, especifique o padrão que será usado para corresponder os números a serem convertidos.
    - No campo **Regra de conversão**, especifique o padrão para o formato dos números convertidos.

    Por exemplo, se você inserir ** ^ \+(\d{9}\d +) $** em **corresponder este padrão** e **011 $1** em **regra de conversão**, a regra converterá + 441235551010 para 011441235551010.
8. Clique em **OK** para salvar a regra de tradução.
9. Clique em **OK** para salvar a configuração de tronco.
10. Na página **Configuração do Tronco**, clique em **Confirmar** e clique em **Confirmar tudo**. 

> [!Note] 
> Sempre que criar ou modificar uma regra de tradução, será necessário executar o comando **Confirmar tudo** para publicar a alteração de configuração. Para obter detalhes, consulte [Publish Pending Changes to The Voice Routing Configuration](https://technet.microsoft.com/library/gg413088(v=ocs.15).aspx). 
