---
title: Criar ou modificar uma regra de normalização no Skype para negócios
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e8547d7b-f74d-4a73-9a7d-df20d7a87fcd
description: 'Resumo: Saiba como definir, criar e modificar uma regra de normalização no Skype para Business Server.'
ms.openlocfilehash: d9c56d96c0eb9069e4ec02b196a326ad8b599e75
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20972545"
---
# <a name="create-or-modify-a-normalization-rule-in-skype-for-business"></a>Criar ou modificar uma regra de normalização no Skype para negócios
 
**Resumo:** Saiba como definir, criar e modificar uma regra de normalização no Skype para Business Server.
  
Definir, criar e modificar as regras de normalização no Skype para Business Server.
  
### <a name="to-define-a-normalization-rule-by-using-build-a-normalization-rule"></a>Para definir uma regra de normalização usando Compilar uma Regra de Normalização

1. Abra o Skype para painel de controle do servidor de negócios
    
2. (Opcional) Siga as etapas em [criar ou modificar um plano de discagem no Skype para Business Server](dial-plans.md) por meio da etapa 11 ou [Modify a Dial Plan](http://technet.microsoft.com/library/a91f02df-cf60-40cf-82fe-e0342c118b91.aspx) até a etapa 10.
    
3. Na **Nova regra de normalização** ou **Editar regra de normalização**, digite um nome que descreva o padrão numérico que está sendo normalizado em **nome** (por exemplo, 5DigitExtension).
    
4. (Opcional) Em **Descrição**, digite uma descrição da regra de normalização (por exemplo, "Converte extensões de cinco dígitos").
    
5. Em **Compilar uma Regra de Normalização**, digite valores nos campos a seguir:
    
   - **Dígitos iniciais** (Opcional) Especifica os dígitos dos números discados que você deseja que o padrão corresponda. Por exemplo, type425 se quiser que o padrão corresponda discado números que começam com 425.
    
   - **Comprimento** Especifique o número de dígitos no padrão correspondido e selecione se você deseja que o padrão para corresponder a esse comprimento exatamente, correspondência discado números que são pelo menos esse comprimento ou números de qualquer tamanho de discados de correspondência.
    
   - **Dígitos a serem removidos** (Opcional) Especifique o número de dígitos a serem removidas dos números discados aos iniciais você deseja que o padrão para corresponder.
    
   - **Dígitos a adicionar** (Opcional) Especifica os dígitos a ser adicionado à números discados que você deseja que o padrão corresponda.
    
    Os valores inseridos nesses campos são refletidos em **Padrão a ser correspondido** e **Regra de conversão**. Por exemplo, se você deixar type7 de **dígitos iniciando** vazio, no campo de **comprimento** e selecione **exatamente**e especifica 0 em **dígitos a serem removidos**, a expressão regular resultante no **padrão para corresponder** é:
    
    ^(\d{7})$
    
6. Em **Regra de conversão**, especifique um padrão para o formato de números de telefone E.164 convertido da seguinte maneira:
    
   - Um valor que representa o número de dígitos especificado no padrão de correspondência. Por exemplo, se o padrão de correspondência ^(\d{7})$ e$ 1 na tradução dos números discados de 7 dígitos representa da regra.
    
   - (Opcional) Digite um valor no campo **dígitos a adicionar** para especificar os dígitos a serem anexados ao número convertido (por exemplo, + 1425).
    
    Por exemplo, se contiver **padrão para corresponder** ^(\d{7})$ como o padrão para números discados aos quais e contém **a regra de conversão** + 1425$ 1 como o padrão para e. 164 números de telefone, a regra normaliza 5550100 para + 14255550100.
    
7. (Opcional) Se a regra de normalização resulta em um número de telefone interno à sua organização, selecione **Extensão interna**.
    
8. (Opcional) Insira um número para testar a regra de normalização e clique em **Ir**. Os resultados do teste são exibidos em **Inserir um número para testar**.
    
    > [!NOTE]
    > É possível salvar uma regra de normalização que ainda não passou no teste e reconfigurá-la posteriormente. Para obter detalhes, consulte [Testar roteamento de voz](http://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx). 
  
9. Clique em **OK** para salvar a regra de normalização.
    
10. Clique em **OK** para salvar o plano de discagem.
    
11. Na página **Plano de Discagem**, clique em **Confirmar** e clique em **Confirmar tudo**. 
    
    > [!NOTE]
    > Sempre que criar ou alterar uma regra de normalização, você deve executar o comando **Confirmar todos** para publicar a alteração na configuração. Para obter detalhes, consulte [Publish alterações pendentes para a configuração de roteamento de voz no Skype para negócios](voice-route-config-changes.md) na documentação operações.
  
### <a name="to-define-a-normalization-rule-manually"></a>Para definir uma regra de normalização manualmente

1. Abra o Skype para painel de controle do servidor de negócios
    
2. (Opcional) Siga as etapas em [criar ou modificar um plano de discagem no Skype para Business Server](dial-plans.md). 
    
3. Na **Nova regra de normalização** ou **Editar regra de normalização**, digite um nome que descreva o padrão numérico que está sendo normalizado em **nome** (por exemplo, nome rule5DigitExtension a normalização).
    
4. (Opcional) No campo **Descrição**, digite uma descrição da regra de normalização (por exemplo, "Traduzir extensões de 5 dígitos").
    
5. Em **Compilar uma regra de normalização**, clique em **Editar**.
    
6. Digite o seguinte em **Digitar uma expressão regular**:
    
   - Em **Corresponder este padrão**, especifique o padrão que você deseja usar para coincidir com o número de telefone discado.
    
   - Em **Regra de conversão**, especifique um padrão para o formato dos números de telefone E.164 convertidos.
    
    Por exemplo, se você digitar ^(\d{7})$ em **corresponder este padrão** e + 1425$ 1 em **regra de conversão**, a regra normaliza 5550100 para + 14255550100.
    
7. (Opcional) Se a regra de normalização resulta em um número de telefone interno à sua organização, selecione **Extensão interna**.
    
8. (Opcional) Insira um número para testar a regra de normalização e clique em **Ir**. Os resultados do teste são exibidos em **Inserir um número para testar**.
    
9. Clique em **OK** para salvar a regra de normalização.
    
10. Clique em **OK** para salvar o plano de discagem.
    
11. Na página **Plano de Discagem**, clique em **Confirmar** e clique em **Confirmar tudo**.
    
    > [!NOTE]
    > Sempre que criar ou alterar uma regra de normalização, você deve executar o comando **Confirmar todos** para publicar a alteração na configuração. Para obter detalhes, consulte [Publish alterações pendentes para a configuração de roteamento de voz no Skype para negócios](voice-route-config-changes.md) na documentação operações.
  

