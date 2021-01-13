---
title: Definindo regras de normalização no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: As regras de normalização do Skype for Business Server usam expressões regulares do .NET Framework para converter números de telefone discados para o formato E.164; em outras palavras, as regras de normalização levam o número de telefone discado por um usuário e convertem esse número no formato usado internamente pelo Skype for Business Server. Cada plano de discagem deve ter uma ou mais regras de normalização atribuídas.
ms.openlocfilehash: d4e248dc9b814610df544bca9d932a29756a80b0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823371"
---
# <a name="defining-normalization-rules-in-skype-for-business-server"></a>Definindo regras de normalização no Skype for Business Server

As regras de normalização do Skype for Business Server usam expressões regulares do .NET Framework para converter números de telefone discados para o formato E.164; em outras palavras, as regras de normalização levam o número de telefone discado por um usuário e convertem esse número no formato usado internamente pelo Skype for Business Server. Cada plano de discagem deve ter uma ou mais regras de normalização atribuídas.

Para obter detalhes sobre regras de normalização, consulte [Planos de discagem e regras de normalização.](https://technet.microsoft.com/library/gg413082(v=ocs.15).aspx)

Para obter detalhes sobre como escrever expressões regulares, consulte [Expressões Regulares do .NET Framework.](https://go.microsoft.com/fwlink/p/?linkId=140927)

É possível usar um dos seguintes métodos para definir ou editar uma regra de normalização:
- Use a ferramenta Criar uma Regra de [ **Normalização**](#create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule) para especificar valores para os dígitos inciais, o comprimento, os dígitos a remover e os dígitos a adicionar e, em seguida, permitir que o Painel de Controle do Skype for Business Server gere o padrão de correspondência correspondente e a regra de conversão para você.
- [Escreva expressões regulares manualmente](#create-or-modify-a-normalization-rule-manually) para definir o padrão de correspondência e a regra de conversão. 

## <a name="create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule"></a>Criar ou modificar uma regra de normalização usando Criar uma Regra de Normalização

Conclua as etapas a seguir se quiser criar ou modificar uma regra de normalização no Painel de Controle do Skype for Business Server. 

**Para definir uma regra usando Compilar uma Regra de Normalização**

1. Faça logon no computador como membro do grupo RTCUniversalServerAdmins ou como membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Para obter detalhes, consulte [Delegate setup permissions](https://technet.microsoft.com/library/gg412735(v=ocs.15).aspx).
2. Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o Painel de Controle do Skype for Business, consulte Instalar e [abrir ferramentas administrativas.](../../management-tools/install-and-open-administrative-tools.md)
3. (Opcional) Siga as etapas em [Criar um plano de discagem](https://docs.microsoft.com/skypeforbusiness/deploy/deploy-enterprise-voice/dial-plans#to-create-a-dial-plan) até a etapa 11 ou Modificar um plano de [discagem](https://docs.microsoft.com/skypeforbusiness/deploy/deploy-enterprise-voice/dial-plans#to-modify-a-dial-plan) até a etapa 10. 
4. Em **Nova Regra de Normalização** ou **Editar Regra de Normalização**, digite um nome que descreva o padrão numérico que está sendo normalizado em **Nome** (por exemplo, **5DigitExtension**).
5. (Opcional) Em **Descrição**, digite uma descrição da regra de normalização (por exemplo, "Converte extensões de cinco dígitos").
6. Em **Compilar uma Regra de Normalização**, digite valores nos campos a seguir:
    - **Dígitos inativos:**(Opcional) Especifique os dígitos ins elevadados dos números discados aos quais você deseja que o padrão seja semelhante. Por exemplo, digite **425** se quiser que o padrão corresponda aos números discados que comecem com 425.
    - **Comprimento:** especifique o número de dígitos no padrão de correspondência e selecione se deseja que o padrão corresponder exatamente a esse comprimento, corresponder aos números discados que têm pelo menos esse tamanho ou corresponder aos números discados de qualquer tamanho.
    - **Dígitos a serem removidos:**(Opcional) Especifique o número de dígitos inativos a serem removidos dos números discados que você deseja que o padrão corresponder.
    - **Dígitos a serem adicionados:**(Opcional) Especifique os dígitos a serem adicionados aos números discados aos quais você deseja que o padrão seja semelhante.
    
    Os valores inseridos nesses campos são refletidos em **Padrão a ser correspondido** e **Regra de conversão**. For example, if you leave **Starting digits** empty, type **7** into the **Length** field select **Exactly**, and specify **0** in **Digits to remove**, the resulting regular expression in the Pattern **to match** is:

    **^(\d {7} )$**

7. Em **Regra de conversão**, especifique um padrão para o formato de números de telefone E.164 convertido da seguinte maneira:
    - Um valor que representa o número de dígitos especificado no padrão de correspondência. Por exemplo, se o padrão de correspondência for **^(\d {7} )$**, então $1 na regra de conversão representará números discados de sete dígitos.
    - (Opcional) Digite um valor no campo **Dígitos a adicionar** para especificar os dígitos a serem anexados ao número convertido, (por exemplo **+1425**).
    
    Por exemplo, se Pattern **to match** contiver **^(\d {7} )$** como padrão para números discados e a regra de conversão contiver **+1425$1** como padrão para números de telefone E.164, a regra normalizará de 5550100 a +14255550100. 

8. (Opcional) Se a regra de normalização resultar em um número de telefone interno em sua organização, selecione **Extensão interna**.
9. (Opcional) Insira um número para testar a regra de normalização e clique em **Ir**. Os resultados do teste são exibidos em **Inserir um número para testar**.
    > [!Note] 
    > É possível salvar uma regra de normalização que ainda não passou no teste e reconfigurá-la posteriormente. Para obter detalhes, consulte [Testar roteamento de voz.](https://technet.microsoft.com/library/gg398915(v=ocs.15).aspx) 

10. Clique em **OK** para salvar a regra de normalização.
11. Clique em **OK** para salvar o plano de discagem.
12. Na página **Plano de Discagem**, clique em **Confirmar** e clique em **Confirmar tudo**. 
    > [!Note]
    > Sempre que criar ou alterar uma regra de normalização, você deve executar o comando Confirmar todos para publicar a alteração na configuração. Para obter detalhes, [consulte Publicar alterações pendentes na configuração de roteamento de voz.](https://technet.microsoft.com/library/gg413088(v=ocs.15).aspx) 

## <a name="create-or-modify-a-normalization-rule-manually"></a>Criar ou modificar uma regra de normalização manualmente

Conclua as etapas a seguir para criar ou modificar uma regra de normalização manualmente.

**Para definir uma regra de normalização manualmente**

1. Faça logon no computador como membro do grupo RTCUniversalServerAdmins ou como membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Para obter detalhes, consulte [Delegate setup permissions](https://technet.microsoft.com/library/gg412735(v=ocs.15).aspx).
2. Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o Painel de Controle do Skype for Business, consulte Instalar e [abrir ferramentas administrativas.](../../management-tools/install-and-open-administrative-tools.md)
3. (Opcional) Siga as etapas em [Criar um plano de discagem](GET LINK AFTER MIGRATION) até a etapa 11 ou Modificar um plano de [discagem](GET LINK AFTER MIGRATION) até a etapa 10.  
4. Em **Nova regra de normalização** ou **Editar regra de normalização**, digite um nome que descreve o padrão de número que está sendo normalizado em **Nome** (por exemplo, o nome da regra de normalização **5DigitExtension**).
5. (Opcional) Em **Descrição**, digite uma descrição da regra de normalização (por exemplo, "Converte extensões de cinco dígitos").
6. Em **Criar uma regra de normalização**, clique em **Editar**.
7. Digite o seguinte em Digitar uma expressão regular:
    - Em **Corresponder este padrão**, especifique o padrão que você deseja usar para coincidir com o número de telefone discado.
    - Em **Regra de tradução**, especifique um padrão para o formato dos números de telefone E.164 traduzidos.

    Por exemplo, se você inserir **^(\d {7} )$** em Corresponder a esse padrão e **+1425$1** na regra de conversão, a regra normaliza 5550100 a +14255550100.  

8. (Opcional) Se a regra de normalização resultar em um número de telefone interno em sua organização, selecione **Extensão interna**.
9. (Opcional) Insira um número para testar a regra de normalização e clique em **Ir**. Os resultados do teste são exibidos em **Inserir um número para testar**.

    > [!Note]
    > É possível salvar uma regra de normalização que ainda não passou no teste e reconfigurá-la posteriormente. Para obter detalhes, consulte [Testar roteamento de voz.](https://technet.microsoft.com/library/gg398915(v=ocs.15).aspx) 

10. Clique em **OK** para salvar a regra de normalização.
11. Clique em **OK** para salvar o plano de discagem.
12. Na página **Plano de Discagem,** clique em **Commi** t e em **Commit all**. 
