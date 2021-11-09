---
title: Definindo regras de normalização em Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Skype for Business Server regras de normalização usam .NET Framework expressões regulares para traduzir números de telefone discados para o formato E.164; em outras palavras, as regras de normalização levam o número de telefone discado por um usuário e convertem esse número no formato usado internamente por Skype for Business Server. Cada plano de discagem deve ter uma ou mais regras de normalização atribuídas.
ms.openlocfilehash: 0319a27dd7a6f0d42fffb4e65fcf71fe152cec18
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60859908"
---
# <a name="defining-normalization-rules-in-skype-for-business-server"></a>Definindo regras de normalização em Skype for Business Server

Skype for Business Server regras de normalização usam .NET Framework expressões regulares para traduzir números de telefone discados para o formato E.164; em outras palavras, as regras de normalização levam o número de telefone discado por um usuário e convertem esse número no formato usado internamente por Skype for Business Server. Cada plano de discagem deve ter uma ou mais regras de normalização atribuídas.

Para obter detalhes sobre regras de normalização, consulte [Planos de discagem e regras de normalização.](/previous-versions/office/lync-server-2013/lync-server-2013-dial-plans-and-normalization-rules)

Para obter detalhes sobre como escrever expressões regulares, [consulte .NET Framework Expressões Regulares](/dotnet/standard/base-types/regular-expressions).

É possível usar um dos seguintes métodos para definir ou editar uma regra de normalização:
- Use a ferramenta Criar uma Regra de [ **Normalização**](#create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule) para especificar valores para os dígitos, comprimento, dígitos a ser removidos e dígitos a adicionar e, em seguida, permitir que o Painel de Controle Skype for Business Server gere o padrão correspondente e a regra de conversão para você.
- [Escreva expressões regulares manualmente para](#create-or-modify-a-normalization-rule-manually) definir o padrão correspondente e a regra de conversão. 

## <a name="create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule"></a>Criar ou modificar uma regra de normalização usando Build a Normalization Rule

Conclua as etapas a seguir se quiser criar ou modificar uma regra de normalização Skype for Business Server Painel de Controle. 

**Para definir uma regra usando Compilar uma Regra de Normalização**

1. Faça logon no computador como membro do grupo RTCUniversalServerAdmins ou como membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Para obter detalhes, consulte [Delegate setup permissions](/previous-versions/office/lync-server-2013/lync-server-2013-delegate-setup-permissions).
2. Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle Skype for Business, consulte [Instalar e abrir ferramentas administrativas.](../../management-tools/install-and-open-administrative-tools.md)
3. (Opcional) Siga as etapas em [Criar um plano de discagem](../../deploy/deploy-enterprise-voice/dial-plans.md#to-create-a-dial-plan) através da etapa 11 ou Modificar um plano de [discagem através](../../deploy/deploy-enterprise-voice/dial-plans.md#to-modify-a-dial-plan) da etapa 10. 
4. Em **Nova Regra de Normalização** ou **Editar Regra de Normalização**, digite um nome que descreva o padrão numérico que está sendo normalizado em **Nome** (por exemplo, **5DigitExtension**).
5. (Opcional) Em **Descrição**, digite uma descrição da regra de normalização (por exemplo, "Converte extensões de cinco dígitos").
6. Em **Compilar uma Regra de Normalização**, digite valores nos campos a seguir:
    - **Dígitos in-locar:**(Opcional) Especifique os dígitos principais dos números discados que você deseja que o padrão corresponder. Por exemplo, digite **425** se quiser que o padrão corresponda aos números discados que comecem com 425.
    - **Comprimento**: especifique o número de dígitos no padrão correspondente e selecione se você deseja que o padrão corresponde a esse comprimento exatamente, corresponder a números discados com pelo menos esse tamanho ou corresponder a números discados de qualquer comprimento.
    - **Dígitos a serem removidos:**(Opcional) Especifique o número de dígitos inativos a serem removidos dos números discados que você deseja que o padrão corresponder.
    - **Dígitos a serem adicionados:**(Opcional) Especifique dígitos a serem adicionados aos números discados que você deseja que o padrão corresponder.
    
    Os valores inseridos nesses campos são refletidos em **Padrão a ser correspondido** e **Regra de conversão**. Por exemplo, se você deixar dígitos In-locar **vazios,** digite **7** no campo Comprimento selecione **Exatamente** e especifique **0** em **Dígitos** a ser removido , a expressão regular resultante no **Padrão** a ser corresponder é: 

    **^(\d {7} )$**

7. Em **Regra de conversão**, especifique um padrão para o formato de números de telefone E.164 convertido da seguinte maneira:
    - Um valor que representa o número de dígitos especificado no padrão de correspondência. Por exemplo, se o padrão correspondente for **^(\d {7} )$**, $1 na regra de conversão representará números discados de 7 dígitos.
    - (Opcional) Digite um valor no campo **Dígitos a adicionar** para especificar os dígitos a serem anexados ao número convertido, (por exemplo **+1425**).
    
    Por exemplo, se **Pattern to match** contiver **^(\d {7} )$** como o padrão para números discados e a regra de conversão contiver **+1425$1** como o padrão para números de telefone E.164, a regra normaliza 5550100 a +14255550100. 

8. (Opcional) Se a regra de normalização resultar em um número de telefone interno em sua organização, selecione **Extensão interna**.
9. (Opcional) Insira um número para testar a regra de normalização e clique em **Ir**. Os resultados do teste são exibidos em **Inserir um número para testar**.
    > [!Note] 
    > É possível salvar uma regra de normalização que ainda não passou no teste e reconfigurá-la posteriormente. Para obter detalhes, consulte [Test voice routing](/previous-versions/office/lync-server-2013/lync-server-2013-test-voice-routing). 

10. Clique em **OK** para salvar a regra de normalização.
11. Clique em **OK** para salvar o plano de discagem.
12. Na página **Plano de Discagem**, clique em **Confirmar** e clique em **Confirmar tudo**. 
    > [!Note]
    > Sempre que criar ou alterar uma regra de normalização, você deve executar o comando Confirmar todos para publicar a alteração na configuração. Para obter detalhes, [consulte Publicar alterações pendentes na configuração de roteamento de voz](/previous-versions/office/lync-server-2013/lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration). 

## <a name="create-or-modify-a-normalization-rule-manually"></a>Criar ou modificar uma regra de normalização manualmente

Conclua as etapas a seguir para criar ou modificar uma regra de normalização manualmente.

**Para definir uma regra de normalização manualmente**

1. Faça logon no computador como membro do grupo RTCUniversalServerAdmins ou como membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Para obter detalhes, consulte [Delegate setup permissions](/previous-versions/office/lync-server-2013/lync-server-2013-delegate-setup-permissions).
2. Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle Skype for Business, consulte [Instalar e abrir ferramentas administrativas.](../../management-tools/install-and-open-administrative-tools.md)
3. (Opcional) Siga as etapas em [Criar um plano de discagem](GET LINK AFTER MIGRATION) através da etapa 11 ou Modificar um plano de [discagem através](GET LINK AFTER MIGRATION) da etapa 10.  
4. Em **Nova regra de normalização** ou **Editar regra de normalização**, digite um nome que descreve o padrão de número que está sendo normalizado em **Nome** (por exemplo, o nome da regra de normalização **5DigitExtension**).
5. (Opcional) Em **Descrição**, digite uma descrição da regra de normalização (por exemplo, "Converte extensões de cinco dígitos").
6. Em **Criar uma regra de normalização**, clique em **Editar**.
7. Digite o seguinte em Digitar uma expressão regular:
    - Em **Corresponder este padrão**, especifique o padrão que você deseja usar para coincidir com o número de telefone discado.
    - Em **Regra de tradução**, especifique um padrão para o formato dos números de telefone E.164 traduzidos.

    Por exemplo, se você inserir **^(\d {7} )$** em Corresponder a esse padrão e **+1425$1** **na** regra de conversão, a regra normaliza 5550100 para +14255550100. 

8. (Opcional) Se a regra de normalização resultar em um número de telefone interno em sua organização, selecione **Extensão interna**.
9. (Opcional) Insira um número para testar a regra de normalização e clique em **Ir**. Os resultados do teste são exibidos em **Inserir um número para testar**.

    > [!Note]
    > É possível salvar uma regra de normalização que ainda não passou no teste e reconfigurá-la posteriormente. Para obter detalhes, consulte [Test voice routing](/previous-versions/office/lync-server-2013/lync-server-2013-test-voice-routing). 

10. Clique em **OK** para salvar a regra de normalização.
11. Clique em **OK** para salvar o plano de discagem.
12. Na página **Plano de Discagem,** clique em **Commi** t e clique em **Comprometer tudo.**