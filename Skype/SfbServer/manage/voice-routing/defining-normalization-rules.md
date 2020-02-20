---
title: Definindo regras de normalização no Skype for Business Server
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
description: As regras de normalização do Skype for Business Server usam expressões regulares do .NET Framework para converter números de telefone discados em formato E. 164; em outras palavras, as regras de normalização levam o número de telefone discado por um usuário e convertem esse número no formato usado internamente pelo Skype for Business Server. Cada plano de discagem deve ter uma ou mais regras de normalização atribuídas.
ms.openlocfilehash: 2fd7f59bcebcfe676a03ce5a6a897336551ddbad
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151211"
---
# <a name="defining-normalization-rules-in-skype-for-business-server"></a>Definindo regras de normalização no Skype for Business Server

As regras de normalização do Skype for Business Server usam expressões regulares do .NET Framework para converter números de telefone discados em formato E. 164; em outras palavras, as regras de normalização levam o número de telefone discado por um usuário e convertem esse número no formato usado internamente pelo Skype for Business Server. Cada plano de discagem deve ter uma ou mais regras de normalização atribuídas.

Para obter detalhes sobre as regras de normalização, consulte [Dial Plans and Normalization Rules](https://technet.microsoft.com/library/gg413082(v=ocs.15).aspx).

Para obter detalhes sobre como escrever expressões regulares, consulte [expressões regulares do .NET Framework](https://go.microsoft.com/fwlink/p/?linkId=140927).

É possível usar um dos seguintes métodos para definir ou editar uma regra de normalização:
- [Use a ferramenta **criar uma regra de normalização** ](#create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule) para especificar valores para os dígitos iniciais, comprimento, dígitos a serem removidos e dígitos a serem adicionados e permitir que o painel de controle do Skype for Business Server gere o padrão correspondente e a regra de conversão para você.
- [Escreva expressões regulares manualmente](#create-or-modify-a-normalization-rule-manually) para definir o padrão de correspondência e a regra de conversão. 

## <a name="create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule"></a>Criar ou modificar uma regra de normalização usando a criação de uma regra de normalização

Complete as etapas a seguir se quiser criar ou modificar uma regra de normalização no painel de controle do Skype for Business Server. 

**Para definir uma regra usando Compilar uma Regra de Normalização**

1. Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Para obter detalhes, consulte [delegar permissões de configuração](https://technet.microsoft.com/library/gg412735(v=ocs.15).aspx).
2. Abra uma janela do navegador e insira a URL do administrador para abrir o painel de controle. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Skype for Business, consulte [instalar e abrir ferramentas administrativas](../../management-tools/install-and-open-administrative-tools.md).
3. Opcion Siga as etapas em [criar um plano de discagem](https://docs.microsoft.com/skypeforbusiness/deploy/deploy-enterprise-voice/dial-plans#to-create-a-dial-plan) até a etapa 11 ou [modificar um plano de discagem](https://docs.microsoft.com/skypeforbusiness/deploy/deploy-enterprise-voice/dial-plans#to-modify-a-dial-plan) até a etapa 10. 
4. Em **Nova Regra de Normalização** ou **Editar Regra de Normalização**, digite um nome que descreva o padrão numérico que está sendo normalizado em **Nome** (por exemplo, **5DigitExtension**).
5. (Opcional) Em **Descrição**, digite uma descrição da regra de normalização (por exemplo, "Converte extensões de cinco dígitos").
6. Em **Compilar uma Regra de Normalização**, digite valores nos campos a seguir:
    - **Dígitos iniciais**: (opcional) especifique os dígitos à esquerda dos números discados que você deseja que o padrão corresponda. Por exemplo, digite **425** se quiser que o padrão corresponda aos números discados que comecem com 425.
    - **Comprimento**: especifique o número de dígitos no padrão de correspondência e selecione se deseja que o padrão corresponda exatamente a esse tamanho, coincidir números discados com pelo menos esse comprimento ou coincidir números discados de qualquer tamanho.
    - **Dígitos a serem**removidos: (opcional) especifique o número de dígitos iniciais a serem removidos dos números discados aos quais você deseja que o padrão corresponda.
    - **Dígitos a serem**adicionados: (opcional) especifique os dígitos a serem adicionados aos números discados que você deseja que o padrão corresponda.
    
    Os valores inseridos nesses campos são refletidos em **Padrão a ser correspondido** e **Regra de conversão**. Por exemplo, se você deixar os **dígitos iniciais** vazios, digite **7** no campo **comprimento** selecione **exatamente**e especifique **0** em **dígitos a serem removidos**, a expressão regular resultante no **padrão a ser correspondido** é:

    **^ (\d{7}) $**

7. Em **Regra de conversão**, especifique um padrão para o formato de números de telefone E.164 convertido da seguinte maneira:
    - Um valor que representa o número de dígitos especificado no padrão de correspondência. Por exemplo, se o padrão de correspondência for **^ ({7}\d) $**, então $1 na regra de conversão representarão números discados de sete dígitos.
    - (Opcional) Digite um valor no campo **Dígitos a adicionar** para especificar os dígitos a serem anexados ao número convertido, (por exemplo **+1425**).
    
    Por exemplo, se o **padrão a ser correspondido** contiver **^ (\d{7}) $** como o padrão para números discados e a regra de **conversão** contém **+ 1425 $1** como o padrão para números de telefone e. 164, a regra normaliza 5550100 para + 14255550100.

8. (Opcional) Se a regra de normalização resultar em um número de telefone interno em sua organização, selecione **Extensão interna**.
9. (Opcional) Insira um número para testar a regra de normalização e clique em **Ir**. Os resultados do teste são exibidos em **Inserir um número para testar**.
    > [!Note] 
    > É possível salvar uma regra de normalização que ainda não passou no teste e reconfigurá-la posteriormente. Para obter detalhes, consulte [Test Voice Routing](https://technet.microsoft.com/library/gg398915(v=ocs.15).aspx). 

10. Clique em **OK** para salvar a regra de normalização.
11. Clique em **OK** para salvar o plano de discagem.
12. Na página **Plano de Discagem**, clique em **Confirmar** e clique em **Confirmar tudo**. 
    > [!Note]
    > Sempre que criar ou alterar uma regra de normalização, você deve executar o comando Confirmar todos para publicar a alteração na configuração. Para obter detalhes, consulte [Publish Pending Changes to The Voice Routing Configuration](https://technet.microsoft.com/library/gg413088(v=ocs.15).aspx). 

## <a name="create-or-modify-a-normalization-rule-manually"></a>Criar ou modificar uma regra de normalização manualmente

Conclua as etapas a seguir para criar ou modificar uma regra de normalização manualmente.

**Para definir uma regra de normalização manualmente**

1. Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Para obter detalhes, consulte [delegar permissões de configuração](https://technet.microsoft.com/library/gg412735(v=ocs.15).aspx).
2. Abra uma janela do navegador e insira a URL do administrador para abrir o painel de controle. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Skype for Business, consulte [instalar e abrir ferramentas administrativas](../../management-tools/install-and-open-administrative-tools.md).
3. Opcion Siga as etapas em [criar um plano de discagem](GET LINK AFTER MIGRATION) até a etapa 11 ou [modificar um plano de discagem](GET LINK AFTER MIGRATION) até a etapa 10.  
4. Em **Nova regra de normalização** ou **Editar regra de normalização**, digite um nome que descreve o padrão de número que está sendo normalizado em **Nome** (por exemplo, o nome da regra de normalização **5DigitExtension**).
5. (Opcional) Em **Descrição**, digite uma descrição da regra de normalização (por exemplo, "Converte extensões de cinco dígitos").
6. Em **Criar uma regra de normalização**, clique em **Editar**.
7. Digite o seguinte em Digitar uma expressão regular:
    - Em **Corresponder este padrão**, especifique o padrão que você deseja usar para coincidir com o número de telefone discado.
    - Em **Regra de tradução**, especifique um padrão para o formato dos números de telefone E.164 traduzidos.

    Por exemplo, se você inserir **^ (\d{7}) $** em **corresponder a este padrão** e **+ 1425 $1** em **regra de conversão**, a regra normaliza 5550100 para + 14255550100.

8. (Opcional) Se a regra de normalização resultar em um número de telefone interno em sua organização, selecione **Extensão interna**.
9. (Opcional) Insira um número para testar a regra de normalização e clique em **Ir**. Os resultados do teste são exibidos em **Inserir um número para testar**.

    > [!Note]
    > É possível salvar uma regra de normalização que ainda não passou no teste e reconfigurá-la posteriormente. Para obter detalhes, consulte [Test Voice Routing](https://technet.microsoft.com/library/gg398915(v=ocs.15).aspx). 

10. Clique em **OK** para salvar a regra de normalização.
11. Clique em **OK** para salvar o plano de discagem.
12. Na página **plano de discagem** , clique em **commi**t e em **confirmar tudo**. 
