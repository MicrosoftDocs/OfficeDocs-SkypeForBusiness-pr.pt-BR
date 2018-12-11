---
title: Definindo regras de normalização no Skype para Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype para regras de normalização Business Server use expressões regulares do .NET Framework para converter números de telefone discado formato e. 164; em outras palavras, as regras de normalização levar o número de telefone discado por um usuário e converta esse número para o formato usado internamente pelo Skype para Business Server. Cada plano de discagem deve ter uma ou mais regras de normalização atribuídas.
ms.openlocfilehash: 1304fa24f469b5ea8735858d3b66637eb404ab25
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222930"
---
# <a name="defining-normalization-rules-in-skype-for-business-server"></a>Definindo regras de normalização no Skype para Business Server

Skype para regras de normalização Business Server use expressões regulares do .NET Framework para converter números de telefone discado formato e. 164; em outras palavras, as regras de normalização levar o número de telefone discado por um usuário e converta esse número para o formato usado internamente pelo Skype para Business Server. Cada plano de discagem deve ter uma ou mais regras de normalização atribuídas.

Para obter detalhes sobre as regras de normalização, consulte [planos de discagem e regras de normalização](https://technet.microsoft.com/en-us/library/gg413082(v=ocs.15).aspx).

Para obter detalhes sobre como escrever expressões regulares, consulte [Expressões regulares do .NET Framework](http://go.microsoft.com/fwlink/p/?linkId=140927).

Você pode usar um dos métodos a seguir para definir ou editar uma regra de normalização:
- [Use a ferramenta **compilar uma regra de normalização** ](#create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule) especificar valores para os dígitos, tamanho, dígitos a serem removidos e dígitos a adicionar e deixe Skype para painel de controle do Business Server gerar correspondentes pattern e translation regra correspondente inicial Para você.
- [Escrever expressões regulares manualmente](#create-or-modify-a-normalization-rule-manually) para definir a regra padrão e uma tradução correspondente. 

## <a name="create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule"></a>Criar ou modificar uma regra de normalização usando compilar uma regra de normalização

Se você deseja criar ou modificar uma regra de normalização no Skype para painel de controle do Business Server, conclua as etapas a seguir. 

**Para definir uma regra usando compilar uma regra de normalização**

1. Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como um membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Para obter detalhes, consulte [permissões de instalação delegadas](https://technet.microsoft.com/en-us/library/gg412735(v=ocs.15).aspx).
2. Abra uma janela do navegador e insira a URL do administrador para abrir o painel de controle. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o Skype para painel de controle corporativos, consulte [Install and abrir ferramentas administrativas](../../management-tools/install-and-open-administrative-tools.md).
3. (Opcional) Siga as etapas em [criar um plano de discagem](GET LINK AFTER MIGRATION) por meio da etapa 11 ou [modificar um plano de discagem](GET LINK AFTER MIGRATION) até a etapa 10. 
4. Em  **Nova Regra de Normalização** ou **Editar Regra de Normalização**, digite um nome que descreva o padrão numérico que está sendo normalizado em **Nome** (por exemplo, **5DigitExtension**).
5. (Opcional) Em **Descrição**, digite uma descrição da regra de normalização (por exemplo, "Converte extensões de cinco dígitos").
6. Em **Compilar uma Regra de Normalização**, digite valores nos campos a seguir:
    - **Dígitos iniciais**: (opcional) Especifique os dígitos à esquerda do discado números que você deseja que o padrão corresponda. Por exemplo, digite **425** se quiser que o padrão corresponda aos números discados que comecem com 425.
    - **Comprimento**: especifique o número de dígitos no padrão de correspondência pattern e selecione se você deseja que o padrão para corresponder a esse comprimento exatamente, correspondência discado números que são pelo menos esse comprimento ou números de qualquer tamanho de discados de correspondência.
    - **Dígitos a serem removidos**: (opcional) Especifique o número de dígitos a serem removidas dos números discados aos iniciais você deseja que o padrão para corresponder.
    - **Dígitos a adicionar**: (opcional) Especifique dígitos a serem adicionados discados números que você deseja que o padrão corresponda.
    
    Os valores inseridos nesses campos são refletidos em **Padrão a ser correspondido** e **Regra de conversão**. Por exemplo, se você deixar vazio **Iniciando dígitos** , tipo **7** no campo **comprimento** selecione **exatamente**e especifique **0** em **dígitos a serem removidos**, a expressão regular resultante no **padrão para corresponder** é:

    **^(\d{7})$**

7. Em **Regra de conversão**, especifique um padrão para o formato de números de telefone E.164 convertido da seguinte maneira:
    - Um valor que representa o número de dígitos especificado no padrão de correspondência. Por exemplo, se o padrão de correspondência **^(\d{7})$**, e em seguida, $1 em regra de conversão representa os números discados de 7 dígitos.
    - (Opcional) Digite um valor no campo **Dígitos a adicionar** para especificar os dígitos a serem anexados ao número convertido, (por exemplo **+1425**).
    
    Por exemplo, se contiver **padrão para corresponder** **^(\d{7})$** como o padrão para a **regra de conversão** e números discados contém **+ 1425$ 1** como padrão para os números de telefone e. 164, a regra normaliza 5550100 para + 14255550100.

8. (Opcional) Se a regra de normalização resulta em um número de telefone interno à sua organização, selecione **Extensão interna**.
9. (Opcional) Insira um número para testar a regra de normalização e clique em **Ir**. Os resultados do teste são exibidos em **Inserir um número para testar**.
    > [!Note] 
    > É possível salvar uma regra de normalização que ainda não passou no teste e reconfigurá-la posteriormente. Para obter detalhes, consulte [Testar roteamento de voz](https://technet.microsoft.com/en-us/library/gg398915(v=ocs.15).aspx). 

10. Clique em **OK** para salvar a regra de normalização.
11. Clique em **OK** para salvar o plano de discagem.
12. Na página **Plano de Discagem**, clique em **Confirmar** e clique em **Confirmar tudo**. 
    > [!Note]
    > Sempre que criar ou alterar uma regra de normalização, você deve executar o comando Confirmar todos para publicar a alteração na configuração. Para obter detalhes, consulte [Publish alterações pendentes para a configuração de roteamento de voz](https://technet.microsoft.com/en-us/library/gg413088(v=ocs.15).aspx). 

## <a name="create-or-modify-a-normalization-rule-manually"></a>Criar ou modificar uma regra de normalização manualmente

Se você deseja criar ou modificar uma regra de normalização manualmente, conclua as etapas a seguir.

**Para definir uma regra de normalização manualmente**

1. Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como um membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Para obter detalhes, consulte [permissões de instalação delegadas](https://technet.microsoft.com/en-us/library/gg412735(v=ocs.15).aspx).
2. Abra uma janela do navegador e insira a URL do administrador para abrir o painel de controle. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o Skype para painel de controle corporativos, consulte [Install and abrir ferramentas administrativas](../../management-tools/install-and-open-administrative-tools.md).
3. (Opcional) Siga as etapas em [criar um plano de discagem](GET LINK AFTER MIGRATION) por meio da etapa 11 ou [modificar um plano de discagem](GET LINK AFTER MIGRATION) até a etapa 10.  
4. Em **Nova regra de normalização** ou **Editar regra de normalização**, digite um nome que descreve o padrão de número que está sendo normalizado em **Nome** (por exemplo, o nome da regra de normalização **5DigitExtension**).
5. (Opcional) Em **Descrição**, digite uma descrição da regra de normalização (por exemplo, "Converte extensões de cinco dígitos").
6. Em **Compilar uma regra de normalização**, clique em **Editar**.
7. Digite o seguinte em Digitar uma expressão regular:
    - Em **Corresponder este padrão**, especifique o padrão que você deseja usar para coincidir com o número de telefone discado.
    - Em **Regra de conversão**, especifique um padrão para o formato dos números de telefone E.164 convertidos.

    Por exemplo, se você digitar **^(\d{7})$** em **corresponder este padrão** e **+ 1425$ 1** na **regra de conversão**, a regra normaliza 5550100 para + 14255550100.

8. (Opcional) Se a regra de normalização resulta em um número de telefone interno à sua organização, selecione **Extensão interna**.
9. (Opcional) Insira um número para testar a regra de normalização e clique em **Ir**. Os resultados do teste são exibidos em **Inserir um número para testar**.

    > [!Note]
    > É possível salvar uma regra de normalização que ainda não passou no teste e reconfigurá-la posteriormente. Para obter detalhes, consulte [Testar roteamento de voz](https://technet.microsoft.com/en-us/library/gg398915(v=ocs.15).aspx). 

10. Clique em **OK** para salvar a regra de normalização.
11. Clique em **OK** para salvar o plano de discagem.
12. Na página de **Plano de discagem** , clique em **Commi**t e clique em **Confirmar tudo**. 