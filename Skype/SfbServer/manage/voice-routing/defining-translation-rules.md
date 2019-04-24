---
title: Definindo regras de conversão no Skype para Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype para Business Server Enterprise Voice roteia as chamadas com base em números de telefone normalizados no formato e. 164. Isso significa que todas as cadeias de caracteres discadas devem ser normalizadas formato e. 164 para fins de executar a pesquisa inversa (RNL) para que eles podem ser traduzidos para seu URI de SIP correspondente. Skype para Business Server fornece a capacidade de manipular o ID chamado e apresentação da ID do chamador.
ms.openlocfilehash: b85241cfa7fc8f14732c92994660cdeb2088c874
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32214649"
---
# <a name="defining-translation-rules-in-skype-for-business-server"></a>Definindo regras de conversão no Skype para Business Server

Skype para Business Server Enterprise Voice roteia as chamadas com base em números de telefone normalizados no formato e. 164. Isso significa que todas as cadeias de caracteres discadas devem ser normalizadas formato e. 164 para fins de executar a pesquisa inversa (RNL) para que eles podem ser traduzidos para seu URI de SIP correspondente. Skype para Business Server fornece a capacidade de manipular o ID chamado e apresentação da ID do chamador.

Com o Skype para Business Server, o número de telefone da parte chamada (ou seja, o número de telefone chamada) pode ser traduzido do formato e. 164 para o formato de discagem local que é exigido pelo ponto do tronco (ou seja, o gateway associado, privada de comutação exchange (PBX) ou SIP tronco). Para fazer isso, você deve definir uma ou mais regras de conversão para converter a URI de Solicitação antes de roteá-la para o ponto de tronco.

## <a name="caller-id-presentation"></a>Apresentação da ID de chamador

Skype para Business Server oferece a opção para traduzir também o número de telefone do chamador (ou seja, o número de telefone que o chamador está chamando) do formato e. 164 para o formato de discagem local que é exigido pelo ponto do tronco. Por exemplo, é possível criar uma regra de conversão para remover o prefixo +44 do início de uma cadeia de caracteres de discagem e substituí-lo por 0144.

**Para configurar a ID do chamador, usando o Skype para painel de controle do Business Server**

1. Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como um membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Para obter detalhes, consulte [permissões de instalação delegadas](https://technet.microsoft.com/en-us/library/gg412735(v=ocs.15).aspx).
2. Abra uma janela do navegador e insira a URL do administrador para abrir o painel de controle. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o Skype para painel de controle corporativos, consulte [Install and abrir ferramentas administrativas](../../management-tools/install-and-open-administrative-tools.md).
3. Na barra de navegação à esquerda, clique em **Roteamento de Voz** e depois, em **Configuração do Tronco**.
4. Na página Configuração do Tronco, clique duas vezes no tronco existente (por exemplo, o tronco **Global**) para exibir a caixa de diálogo **Editar Configuração do Tronco**.
5. Para configurar a apresentação da ID de chamadas:
    - Para escolher uma ou mais regras de uma lista de todas as regras de conversão disponíveis em sua implantação do Enterprise Voice, clique em **Selecionar**. Em **Regras de Conversão de Número de Chamada**, clique nas regras que você deseja associar ao tronco e clique em **OK**.
    - Para definir uma nova regra de conversão e associá-la ao tronco, clique em **Novo**. 
    - Para editar uma regra de conversão que já esteja associada ao tronco, clique no nome da regra e clique em **Exibir detalhes**.
    - Para copiar uma regra existente de conversão a ser usado como um ponto de partida para definir uma nova regra, clique no nome da regra, clique em **Copiar**e, em seguida, clique em **Colar**.
    - Para remover uma regra de conversão do tronco, destaque o nome da regra e clique em **Remover**.

> [!Warning] 
> Não associe regras de conversão a um tronco se não houver regras de conversão configuradas no ponto do tronco associado porque as duas regras podem entrar em conflito. 

## <a name="called-id-presentation"></a>Apresentação da ID chamada

> [!Important]
> A capacidade de associar um ou mais regras de conversão de uma configuração de tronco do Enterprise Voice é destinada a ser usado como uma *alternativa* à configuração de regras de conversão no ponto do tronco. Não associe regras de conversão com uma configuração de tronco do Enterprise Voice se você tiver configurado regras de conversão no ponto do tronco, pois as duas regras podem entrar em conflito. 

Você pode usar um dos métodos a seguir para criar ou modificar uma regra de conversão:

- [Use a ferramenta de uma regra de conversão de compilação](#create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool) para especificar valores para o inicial dígitos, tamanho, dígitos a serem removidos e dígitos a adicionar e deixe o Skype para painel de controle do Business Server gerar correspondentes pattern e translation regra correspondente para você.
- [Escrever expressões regulares manualmente](#create-or-modify-a-translation-rule-manually) para definir a regra padrão e uma tradução correspondente.

> [!Note]
> Para obter informações sobre como escrever expressões regulares, consulte [Expressões regulares do .NET Framework](http://go.microsoft.com/fwlink/p/?linkId=140927). 

### <a name="create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool"></a>Criar ou modificar uma regra de conversão usando a compilação uma ferramenta de regra de conversão

Se você deseja definir uma regra de conversão digitando um conjunto de valores na compilação de uma ferramenta de regra de conversão e habilitando o Skype para painel de controle do Business Server gerar o padrão de correspondência correspondente e uma regra de conversão para você, siga estas etapas. 

**Para definir uma regra usando a ferramenta Compilar uma Regra de Conversão**

1. Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como um membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Para obter detalhes, consulte [permissões de instalação delegadas](https://technet.microsoft.com/en-us/library/gg412735(v=ocs.15).aspx).
2. Abra uma janela do navegador e insira a URL do administrador para abrir o painel de controle. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o Skype para painel de controle corporativos, consulte [Install and abrir ferramentas administrativas](../../management-tools/install-and-open-administrative-tools.md).
3. Para começar a definir uma regra de conversão, siga as etapas em [Configure um tronco com media bypass](GET LINK AFTER MIGRATION)por meio da etapa 10 ou [Configure um tronco sem media bypass](GET LINK AFTER MIGRATION) até a etapa 9.
4. Em  **Nome** na página  **Nova Regra de Conversão** ou **Editar Regra de Conversão**, digite um nome que descreve o padrão numérico que está convertido.
5. (Opcional) Em **Descrição**, digite uma descrição da regra de conversão - por exemplo, **interurbana discagem internacional EUA**.
6. Na seção  **Compilar uma Regra de Conversão** da caixa de diálogo, insira valores nos seguintes campos:
    - **Dígitos iniciais**: (Opcional) especifique os dígitos iniciais dos números com os quais você deseja que o padrão corresponda. Por exemplo, digite  + nesse campo para corresponder os números no formato E.164 (que começa com +).
    - **Comprimento**: especifique o número de dígitos no padrão de correspondência e selecione se deseja que o padrão corresponda a números exatamente com esse comprimento, com um comprimento menor ou qualquer comprimento. Por exemplo, digite  **11** e selecione  **At least** na lista suspensa para fazer a correspondência de números com no mínimo 11 dígitos de comprimento.
    - **Dígitos a serem removidos**: (Opcional) especifique o número de dígitos iniciais a serem removidos. Por exemplo, digite **1** para retirar o + do início do número.
    - **Dígitos a adicionar**: (Opcional) especifique os dígitos a serem anexados aos números convertidos. Por exemplo, digite  **011** se quiser que 011 seja anexado aos números convertidos quando a regra for aplicada.
    
    Os valores inseridos nesses campos serão refletidos nos campos de regra **padrão para corresponder** e uma **tradução** . Por exemplo, se você especificar os valores do exemplo anterior, a expressão regular resultante no campo **padrão para diferenciar**h é:
    
    **^\+(\d{9}\d+)$** 

    O campo  **Regra de conversão** especifica um padrão para o formato de números convertidos. Este padrão possui duas partes:
    - Um valor (por exemplo, **$1**) que representa o número de dígitos no padrão correspondido
    - (Opcional) Um valor que pode ser anexado digitando no campo **dígitos a adicionar**

    Usando os valores do exemplo anterior, **011$ 1** aparece no campo **regra de conversão** .
    
    Quando essa regra de conversão é aplicada, + 441235551010 se torna 011441235551010.
7. Clique em **Okey** para salvar a regra de conversão.
8. Clique em **Okey** para salvar a configuração do tronco.
9. Na página **Configuração de tronco**n, clique em **Confirmar**e clique em **Confirmar tudo**. 

> [!Note]
> Sempre que você cria ou modificar uma regra de conversão, você precisará executar o comando de **Confirmar todos** para publicar a alteração de configuração. Para obter detalhes, consulte [Publish alterações pendentes para a configuração de roteamento de voz](https://technet.microsoft.com/en-us/library/gg413088(v=ocs.15).aspx). 

### <a name="create-or-modify-a-translation-rule-manually"></a>Criar ou modificar uma regra de conversão manualmente

Se você deseja definir uma regra de conversão escrevendo uma expressão regular para o padrão de correspondência e a regra de conversão, siga estas etapas. 

**Para definir uma regra de conversão manualmente**

1. Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como um membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Para obter detalhes, consulte [permissões de instalação delegadas](https://technet.microsoft.com/en-us/library/gg412735(v=ocs.15).aspx).
2. Abra uma janela do navegador e insira a URL do administrador para abrir o painel de controle. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o Skype para painel de controle corporativos, consulte [Install and abrir ferramentas administrativas](../../management-tools/install-and-open-administrative-tools.md).
3. Para começar a definir uma regra de conversão, siga as etapas em [Configure um tronco com media bypass](GET LINK AFTER MIGRATION)por meio da etapa 10 ou [Configure um tronco sem media bypass](GET LINK AFTER MIGRATION) até a etapa 9.
4. No campo **nome** na página **Nova regra de conversão** ou **Editar regra de conversão** , digite um nome que descreva o padrão numérico que está sendo convertido.
5. (Opcional) Em **Descrição**, digite uma descrição da regra de conversão; Por exemplo, **interurbana discagem internacional EUA**.
6. Clique em **Editar** na parte inferior da seção **criar uma regra de conversão** .
7. Insira o seguinte em tipo de uma **Expressão Regular**:
    - Em **corresponder este padrão**, especifique o padrão que será usado para corresponder os números a serem convertidos.
    - Em **regra de conversão**, especifique um padrão para o formato dos números convertidos.

    Por exemplo, se você digitar ** ^ \+(\d{9}\d+)$** em **corresponder este padrão** e **011$ 1** na **regra de conversão**, a regra converterá + 441235551010 em 011441235551010.
8. Clique em **Okey** para salvar a regra de conversão.
9. Clique em **Okey** para salvar a configuração do tronco.
10. Na página **Configuração do Tronco**, clique em **Confirmar** e clique em **Confirmar tudo**. 

> [!Note] 
> Sempre que você cria ou modificar uma regra de conversão, você precisará executar o comando de **Confirmar todos** para publicar a alteração de configuração. Para obter detalhes, consulte [Publish alterações pendentes para a configuração de roteamento de voz](https://technet.microsoft.com/en-us/library/gg413088(v=ocs.15).aspx). 
