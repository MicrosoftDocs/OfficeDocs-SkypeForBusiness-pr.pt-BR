---
title: Definindo regras de normalização no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: As regras de normalização do Skype for Business Server usam expressões regulares do .NET Framework para traduzir números de telefone discados para o formato E. 164; em outras palavras, as regras de normalização recebem o número de telefone discado por um usuário e convertem esse número no formato usado internamente pelo Skype for Business Server. Cada plano de discagem deve ter uma ou mais regras de normalização atribuídas.
ms.openlocfilehash: e5156816de13a8d59e3e6eea4890046d5b4f586a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274974"
---
# <a name="defining-normalization-rules-in-skype-for-business-server"></a>Definindo regras de normalização no Skype for Business Server

As regras de normalização do Skype for Business Server usam expressões regulares do .NET Framework para traduzir números de telefone discados para o formato E. 164; em outras palavras, as regras de normalização recebem o número de telefone discado por um usuário e convertem esse número no formato usado internamente pelo Skype for Business Server. Cada plano de discagem deve ter uma ou mais regras de normalização atribuídas.

Para obter detalhes sobre as regras de normalização, consulte [planos de discagem e regras de normalização](https://technet.microsoft.com/en-us/library/gg413082(v=ocs.15).aspx).

Para obter detalhes sobre como escrever expressões regulares, consulte [expressões regulares do .NET Framework](http://go.microsoft.com/fwlink/p/?linkId=140927).

Você pode usar qualquer um dos seguintes métodos para definir ou editar uma regra de normalização:
- [Use a ferramenta **criar uma regra** ](#create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule) de normalização para especificar valores para os dígitos iniciais, comprimento, dígitos a serem removidos e dígitos a serem adicionados e deixe o painel de controle do Skype for Business Server gerar o padrão correspondente e a regra de tradução Para você.
- [Grave expressões regulares manualmente](#create-or-modify-a-normalization-rule-manually) para definir o padrão correspondente e a regra de tradução. 

## <a name="create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule"></a>Criar ou modificar uma regra de normalização usando criar uma regra de normalização

Conclua as etapas a seguir se desejar criar ou modificar uma regra de normalização no painel de controle do Skype for Business Server. 

**Para definir uma regra usando criar uma regra de normalização**

1. Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como um membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Para obter detalhes, consulte [delegar permissões de configuração](https://technet.microsoft.com/en-us/library/gg412735(v=ocs.15).aspx).
2. Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Skype for Business, confira [instalar e abrir ferramentas administrativas](../../management-tools/install-and-open-administrative-tools.md).
3. Adicionais Siga as etapas em [criar um plano](https://docs.microsoft.com/skypeforbusiness/deploy/deploy-enterprise-voice/dial-plans#to-create-a-dial-plan) de discagem por meio da etapa 11 ou [modifique um plano de discagem](https://docs.microsoft.com/skypeforbusiness/deploy/deploy-enterprise-voice/dial-plans#to-modify-a-dial-plan) pela etapa 10. 
4. Em  **Nova Regra de Normalização** ou **Editar Regra de Normalização**, digite um nome que descreva o padrão numérico que está sendo normalizado em **Nome** (por exemplo, **5DigitExtension**).
5. (Opcional) Em **Descrição**, digite uma descrição da regra de normalização (por exemplo, "Converte extensões de cinco dígitos").
6. Em **Compilar uma Regra de Normalização**, digite valores nos campos a seguir:
    - **Dígitos iniciais**: (opcional) especifique os dígitos à esquerda dos números discados para os quais você deseja que o padrão corresponda. Por exemplo, digite **425** se quiser que o padrão corresponda aos números discados que comecem com 425.
    - **Comprimento**: especifique o número de dígitos no padrão de correspondência e selecione se deseja que o padrão corresponda exatamente a esse comprimento, coincidir números discados com pelo menos esse comprimento ou coincidir números discados de qualquer comprimento.
    - **Dígitos a serem**removidos: (opcional) especifique o número de dígitos iniciais a serem removidos dos números discados que você deseja que o padrão corresponda.
    - **Dígitos a serem**adicionados: (opcional) especifique os dígitos a serem adicionados aos números discados para os quais você deseja que o padrão corresponda.
    
    Os valores inseridos nesses campos são refletidos em **Padrão a ser correspondido** e **Regra de conversão**. Por exemplo, se você deixar os **dígitos iniciais** vazios, digite **7** no **campo comprimento** , selecione **exatamente**e especifique **0** em **dígitos a remover**, a expressão regular resultante no **padrão a ser correspondido** é:

    **^ (\d{7}) $**

7. Em **Regra de conversão**, especifique um padrão para o formato de números de telefone E.164 convertido da seguinte maneira:
    - Um valor que representa o número de dígitos especificado no padrão de correspondência. Por exemplo, se o padrão correspondente for **^ (\d{7}) $**, então $1 na regra de tradução representará os números discados de 7 dígitos.
    - (Opcional) Digite um valor no campo **Dígitos a adicionar** para especificar os dígitos a serem anexados ao número convertido, (por exemplo **+1425**).
    
    Por exemplo, se **a correspondência de padrão** contiver **^{7}(\d) $** como o padrão para números discados e **regra de tradução** contém **+ 1425 $1** como o padrão para os números de telefone e. 164, a regra normaliza o 5550100 para + 14255550100.

8. (Opcional) Se a regra de normalização resulta em um número de telefone interno à sua organização, selecione **Extensão interna**.
9. (Opcional) Insira um número para testar a regra de normalização e clique em **Ir**. Os resultados do teste são exibidos em **Inserir um número para testar**.
    > [!Note] 
    > É possível salvar uma regra de normalização que ainda não passou no teste e reconfigurá-la posteriormente. Para obter detalhes, consulte [testar roteamento de voz](https://technet.microsoft.com/en-us/library/gg398915(v=ocs.15).aspx). 

10. Clique em **OK** para salvar a regra de normalização.
11. Clique em **OK** para salvar o plano de discagem.
12. Na página **Plano de Discagem**, clique em **Confirmar** e clique em **Confirmar tudo**. 
    > [!Note]
    > Sempre que criar ou alterar uma regra de normalização, você deve executar o comando Confirmar todos para publicar a alteração na configuração. Para obter detalhes, consulte [publicar alterações pendentes na configuração de roteamento de voz](https://technet.microsoft.com/en-us/library/gg413088(v=ocs.15).aspx). 

## <a name="create-or-modify-a-normalization-rule-manually"></a>Criar ou modificar uma regra de normalização manualmente

Conclua as etapas a seguir se desejar criar ou modificar uma regra de normalização manualmente.

**Para definir uma regra de normalização manualmente**

1. Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como um membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Para obter detalhes, consulte [delegar permissões de configuração](https://technet.microsoft.com/en-us/library/gg412735(v=ocs.15).aspx).
2. Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Skype for Business, confira [instalar e abrir ferramentas administrativas](../../management-tools/install-and-open-administrative-tools.md).
3. Adicionais Siga as etapas em [criar um plano](GET LINK AFTER MIGRATION) de discagem por meio da etapa 11 ou [modifique um plano de discagem](GET LINK AFTER MIGRATION) pela etapa 10.  
4. Em **Nova regra de normalização** ou **Editar regra de normalização**, digite um nome que descreve o padrão de número que está sendo normalizado em **Nome** (por exemplo, o nome da regra de normalização **5DigitExtension**).
5. (Opcional) Em **Descrição**, digite uma descrição da regra de normalização (por exemplo, "Converte extensões de cinco dígitos").
6. Em **Compilar uma regra de normalização**, clique em **Editar**.
7. Digite o seguinte em Digitar uma expressão regular:
    - Em **Corresponder este padrão**, especifique o padrão que você deseja usar para coincidir com o número de telefone discado.
    - Em **Regra de conversão**, especifique um padrão para o formato dos números de telefone E.164 convertidos.

    Por exemplo, se você inserir **^ (\d{7}) $** em **coincidir este padrão** e **+ 1425 $1** na **regra de tradução**, a regra normalizará 5550100 para + 14255550100.

8. (Opcional) Se a regra de normalização resulta em um número de telefone interno à sua organização, selecione **Extensão interna**.
9. (Opcional) Insira um número para testar a regra de normalização e clique em **Ir**. Os resultados do teste são exibidos em **Inserir um número para testar**.

    > [!Note]
    > É possível salvar uma regra de normalização que ainda não passou no teste e reconfigurá-la posteriormente. Para obter detalhes, consulte [testar roteamento de voz](https://technet.microsoft.com/en-us/library/gg398915(v=ocs.15).aspx). 

10. Clique em **OK** para salvar a regra de normalização.
11. Clique em **OK** para salvar o plano de discagem.
12. Na página **plano** de discagem, **** clique em commi t e, em seguida, clique em **confirmar tudo**. 
