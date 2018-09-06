---
title: Criar ou modificar uma regra de conversão para a apresentação de ID do chamador em Skype para Business Server
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
ms.assetid: 6a643961-a0a1-41d1-96ba-6c428a89d82e
description: 'Resumo: Saiba como configurar o ID do chamador, usando o Skype para painel de controle do Business Server.'
ms.openlocfilehash: 98f2f63584da6a52f4e43b2601073b552518d5b0
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/28/2018
ms.locfileid: "23255368"
---
# <a name="create-or-modify-a-translation-rule-for-caller-id-presentation-in-skype-for-business-server"></a>Criar ou modificar uma regra de conversão para a apresentação de ID do chamador em Skype para Business Server

**Resumo:** Saiba como configurar o ID do chamador, usando o Skype para painel de controle do Business Server.

Com o Skype para Business Server, o número de telefone da parte chamada (ou seja, o número de telefone chamada) pode ser traduzido do formato e. 164 para o formato de discagem local exigidos pelo _ponto de tronco_ (ou seja, o gateway associado, private branch exchange ( PBX), ou tronco SIP). Para fazer isso, você deve definir uma ou mais regras de conversão para converter a URI de Solicitação antes de roteá-la para o ponto de tronco.

Skype para Business Server também lhe também converter o número de telefone do chamador (ou seja, o número de telefone que o chamador está chamando) a opção de formato e. 164 para o formato de discagem local que é exigido pelo ponto do tronco. Por exemplo, é possível criar uma regra de conversão para remover o prefixo +44 do início de uma cadeia de caracteres de discagem e substituí-lo por 0144.

### <a name="to-configure-caller-id-by-using-skype-for-business-server-control-panel"></a>Para configurar a ID do chamador usando Skype para o painel de controle do servidor de negócios

1. Abra o Skype para painel de controle do servidor de negócios.

2. Na barra de navegação à esquerda, clique em **Roteamento de Voz** e depois, em **Configuração do Tronco**.

3. Na página **Configuração do Tronco**, clique duas vezes no tronco existente (por exemplo, o tronco **Global**) para exibir a caixa de diálogo **Editar Configuração do Tronco**.

4. Para configurar a apresentação da ID de chamadas:

   - Para escolher uma ou mais regras de uma lista de todas as regras de conversão disponíveis em sua implantação do Enterprise Voice, clique em **Selecionar**. Em **Regras de Conversão de Número de Chamada**, clique nas regras que você deseja associar ao tronco e clique em **OK**.

   - Para definir uma nova regra de conversão e associá-la ao tronco, clique em **Novo**. Para obter detalhes sobre como definir uma nova regra, consulte [Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) na documentação de implantação.

   - Para editar uma regra de conversão que já esteja associada ao tronco, clique no nome da regra e clique em **Exibir detalhes**. Para obter detalhes, consulte [Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) na documentação de implantação.

   - Para copiar uma regra de conversão existente para usar como ponto de partida para definir uma nova regra, clique no nome da regra e clique em **Copiar** e clique em **Copiar**. Para obter detalhes, consulte [Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx).

   - Para remover uma regra de conversão do tronco, destaque o nome da regra e clique em **Remover**.

    > [!CAUTION]
    > Não associe regras de conversão a um tronco se não houver regras de conversão configuradas no ponto do tronco associado porque as duas regras podem entrar em conflito.


