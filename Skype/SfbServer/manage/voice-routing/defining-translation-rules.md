---
title: Definindo regras de conversão em Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Skype for Business Server Enterprise Voice encaminha chamadas com base em números de telefone normalizados para o formato E.164. Isso significa que todas as cadeias de caracteres discadas devem ser normalizadas para o formato E.164 com a finalidade de executar a RNL (busca de número reverso) para que possam ser traduzidas para o URI SIP correspondente. Skype for Business Server fornece a capacidade de manipular a ID chamada e a apresentação da ID do chamador.
ms.openlocfilehash: bcd0e4f20a237bfbebef5bafcb644721044116ca
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62411514"
---
# <a name="defining-translation-rules-in-skype-for-business-server"></a>Definindo regras de conversão em Skype for Business Server

Skype for Business Server Enterprise Voice encaminha chamadas com base em números de telefone normalizados para o formato E.164. Isso significa que todas as cadeias de caracteres discadas devem ser normalizadas para o formato E.164 com a finalidade de executar a RNL (busca de número reverso) para que possam ser traduzidas para o URI SIP correspondente. Skype for Business Server fornece a capacidade de manipular a ID chamada e a apresentação da ID do chamador.

Com Skype for Business Server, o número de telefone da parte chamada (ou seja, o número de telefone chamado) pode ser convertido do formato E.164 para o formato de discagem local exigido pelo par de tronco (ou seja, o gateway associado, o PBX (private branch exchange) ou o tronco SIP). Para fazer isso, você deve definir uma ou mais regras de conversão para traduzir o URI de solicitação antes de roteá-lo para o ponto de tronco.

## <a name="caller-id-presentation"></a>Apresentação de ID do chamador

Skype for Business Server oferece a opção de também traduzir o número de telefone do chamador (ou seja, o número de telefone do qual o chamador está chamando) do formato E.164 para o formato de discagem local exigido pelo ponto de tronco. Por exemplo, você pode criar uma regra de conversão para remover +44 do começo de uma sequência de caracteres de discagem e o substituir por 0144.

**Para configurar a ID do Chamador usando o painel de Skype for Business Server de controle**

1. Faça logon no computador como membro do grupo RTCUniversalServerAdmins ou como membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Para obter detalhes, consulte [Delegar permissões de instalação](/previous-versions/office/lync-server-2013/lync-server-2013-delegate-setup-permissions).
2. Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle Skype for Business, consulte [Instalar e abrir ferramentas administrativas](../../management-tools/install-and-open-administrative-tools.md).
3. Na barra de navegação esquerda, clique em **Roteamento de Voz** e clique em **Configuração de Tronco**.
4. Na página Configuração do Tronco, clique duas vezes em um tronco existente (por exemplo, o **tronco Global** ) para exibir a caixa de diálogo Editar Configuração **do** Tronco.
5. Para configurar a apresentação da ID do chamador:
    - Para escolher uma ou mais regras em uma lista de todas as regras de conversão disponíveis em sua implantação Enterprise Voice, clique em **Selecionar**. Em **Regras de conversão de número de** chamada, clique nas regras que você deseja associar ao tronco e clique em **OK**.
    - Para definir uma nova regra de conversão e associá-la ao tronco, clique em **Novo**. 
    - Para editar uma regra de conversão que já está associada ao tronco, clique no nome da regra e, depois, em **Mostrar detalhes**.
    - Para copiar uma regra de conversão existente para usar como ponto de partida para definir uma nova regra, clique no nome da regra, em **Copiar** e em **Colar**.
    - Para remover uma regra de conversão do tronco, destaque o nome da regra e clique em **Remover**.

> [!Warning] 
> Não associe regras de conversão a um tronco se você tiver configurado as regras de conversão no ponto de tronco associado, pois as duas regras podem entrar em conflito. 

## <a name="called-id-presentation"></a>Apresentação de ID chamada

> [!Important]
> A capacidade de associar uma ou mais regras de conversão de uma configuração de tronco do Enterprise Voice se destina a ser usada como uma *alternativa* para configurar as regras de conversão no ponto de tronco. Não associe as regras de conversão de uma configuração de tronco Enterprise Voice se você tiver configurado regras de conversão no peer de tronco, porque as duas regras podem entrar em conflito. 

Você pode usar um dos seguintes métodos para compilar ou modificar uma regra de conversão:

- [Use a ferramenta Criar uma](#create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool) Regra de Conversão para especificar valores para os dígitos, comprimento, dígitos a ser removidos e dígitos a adicionar e, em seguida, permitir que o Painel de Controle Skype for Business Server gere o padrão correspondente e a regra de conversão para você.
- [Escreva expressões regulares manualmente para](#create-or-modify-a-translation-rule-manually) definir o padrão correspondente e a regra de conversão.

> [!Note]
> Para obter informações sobre como escrever expressões regulares, [consulte .NET Framework Expressões Regulares](/dotnet/standard/base-types/regular-expressions). 

### <a name="create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool"></a>Criar ou modificar uma regra de conversão usando a ferramenta Criar uma Regra de Conversão

Siga estas etapas se quiser definir uma regra de conversão inserindo um conjunto de valores na ferramenta Criar uma Regra de Conversão e habilitando o Painel de Controle Skype for Business Server para gerar o padrão correspondente e a regra de conversão para você. 

**Para definir uma regra usando a ferramenta Compilar uma Regra de Conversão**

1. Faça logon no computador como membro do grupo RTCUniversalServerAdmins ou como membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Para obter detalhes, consulte [Delegar permissões de instalação](/previous-versions/office/lync-server-2013/lync-server-2013-delegate-setup-permissions).
2. Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle Skype for Business, consulte [Instalar e abrir ferramentas administrativas](../../management-tools/install-and-open-administrative-tools.md).
3. Para começar a definir uma regra de conversão, siga as etapas em [Configure a trunk with media bypassthrough](GET LINK AFTER MIGRATION) step 10 ou [Configure a trunk without media bypass](GET LINK AFTER MIGRATION) through step 9.
4. Em **Nome** na página **Nova Regra de Conversão** ou **Editar Regra de Conversão**, digite um nome que descreve o padrão numérico que está convertido.
5. (Opcional) Em **Descrição**, digite uma descrição da regra de conversão - por exemplo, discagem de **longa distância internacional dos EUA**.
6. Na seção **Compilar uma Regra de Conversão** da caixa de diálogo, insira valores nos seguintes campos:
    - **Dígitos iniciais**: (Opcional) especifique os dígitos iniciais dos números com os quais você deseja que o padrão corresponda. Por exemplo, digite + nesse campo para corresponder os números no formato E.164 (que começa com +).
    - **Comprimento**: especifique o número de dígitos no padrão de correspondência e selecione se deseja que o padrão corresponda a números exatamente com esse comprimento, com um comprimento menor ou qualquer comprimento. Por exemplo, digite **11** e selecione **No mínimo** na lista suspensa para fazer a correspondência de números com no mínimo 11 dígitos de comprimento.
    - **Dígitos a serem removidos**: (Opcional) especifique o número de dígitos iniciais a serem removidos. Por exemplo, digite **1** para retirar o + do início do número.
    - **Dígitos a adicionar**: (Opcional) especifique os dígitos a serem anexados aos números convertidos. Por exemplo, digite **011** se quiser que 011 seja anexado aos números convertidos quando a regra é aplicada.
    
    Os valores que você inserir nesses campos são refletidos nos campos **Padrão para corresponder e** **regra de** conversão. Por exemplo, se você especificar os valores de exemplo anteriores, a expressão regular resultante no **campo Padrão para match** será:
    
    **^\+(\d{9}\d+)$** 

    O campo **Regra de conversão** especifica um padrão para o formato de números convertidos. Esse padrão tem duas partes:
    - Um valor (por exemplo, **$1**) que representa o número de dígitos no padrão correspondido
    - (Opcional) Um valor que pode ser anexado digitando no campo **Dígitos a adicionar**

    Usando os valores do exemplo anterior, **011$1** aparece no campo **Regra de conversão**.
    
    Quando essa regra de conversão é aplicada, +441235551010 se torna 011441235551010.
7. Clique em **OK** para salvar a regra de tradução.
8. Clique em **OK** para salvar a configuração de tronco.
9. Na página **Configuration** do Tronco, clique em **Confirmação** e clique em **Comprometer tudo**. 

> [!Note]
> Sempre que criar ou modificar uma regra de tradução, será necessário executar o comando **Confirmar tudo** para publicar a alteração de configuração. Para obter detalhes, consulte [Publicar alterações pendentes na configuração de roteamento de voz](/previous-versions/office/lync-server-2013/lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration). 

### <a name="create-or-modify-a-translation-rule-manually"></a>Criar ou modificar uma regra de conversão manualmente

Siga estas etapas para definir uma regra de conversão desenvolvendo uma expressão regular para o padrão de correspondência e a regra de conversão. 

**Como definir uma regra de conversão manualmente**

1. Faça logon no computador como membro do grupo RTCUniversalServerAdmins ou como membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Para obter detalhes, consulte [Delegar permissões de instalação](/previous-versions/office/lync-server-2013/lync-server-2013-delegate-setup-permissions).
2. Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle Skype for Business, consulte [Instalar e abrir ferramentas administrativas](../../management-tools/install-and-open-administrative-tools.md).
3. Para começar a definir uma regra de conversão, siga as etapas em [Configure a trunk with media bypassthrough](GET LINK AFTER MIGRATION) step 10 ou [Configure a trunk without media bypass](GET LINK AFTER MIGRATION) through step 9.
4. No campo **Nome**, na página **Nova Regra de Conversão** ou **Editar Regra de Conversão**, digite um nome que descreva o padrão de número sendo convertido.
5. (Opcional) Em **Descrição**, digite uma descrição da regra de conversão; por exemplo, **discagem de longa distância internacional dos EUA**.
6. Clique em **Editar** na parte inferior da seção **Criar uma Regra de Conversão**.
7. Insira o seguinte em Digite uma **expressão regular**:
    - No campo **Corresponder a este padrão**, especifique o padrão que será usado para corresponder os números a serem convertidos.
    - No campo **Regra de conversão**, especifique o padrão para o formato dos números convertidos.

    Por  exemplo, **^\+se você inserir (\d{9}\d+)$** em Corresponder a esse padrão e **011$1** na regra de conversão, a regra traduzirá +441235551010 para 011441235551010.
8. Clique em **OK** para salvar a regra de tradução.
9. Clique em **OK** para salvar a configuração de tronco.
10. Na página **Configuração do Tronco**, clique em **Confirmar** e clique em **Confirmar tudo**. 

> [!Note] 
> Sempre que criar ou modificar uma regra de tradução, será necessário executar o comando **Confirmar tudo** para publicar a alteração de configuração. Para obter detalhes, consulte [Publicar alterações pendentes na configuração de roteamento de voz](/previous-versions/office/lync-server-2013/lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration).