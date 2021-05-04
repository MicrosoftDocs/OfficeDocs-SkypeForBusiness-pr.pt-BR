---
title: Configurar uma conta Microsoft 365 Business Voice de recursos
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: Saiba como configurar uma conta de recurso Microsoft 365 Business Voice para uso com os atendentes automáticos.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 76e91a650e9e72c21a39d292e32fe5ff8ecbf80b
ms.sourcegitcommit: 49cdcf344c63c805bcb6365804c6f5d1393e926a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2021
ms.locfileid: "52130312"
---
# <a name="step-4-set-up-a-business-voice-resource-account"></a>Etapa 4: Configurar uma conta de recurso do Business Voice

Em Microsoft Teams, uma conta de recurso é necessária para cada atendimento automático ou fila de chamada. Contas de recursos também podem ser atribuídas a números de telefone de serviço. É assim que você atribui números de telefone a atendimentos automáticos e filas de chamadas permitindo que os chamadores de fora Teams para alcançar o atendimento automático ou fila de chamadas.

## <a name="obtain-virtual-user-licenses"></a>Obter licenças de usuário virtual

As contas de recursos exigem uma licença para trabalhar com os atendimentos automáticos e filas de chamada. Você pode usar uma licença de *Microsoft 365 Sistema de Telefonia - Usuário Virtual.*

1. Acesse o Centro de administração do Microsoft 365.
2. Acesse **Complementos dos serviços**  >  **de Compra** de  >  **Cobrança** Consulte  >  **todos os produtos de complementos**
3. Role até o final para encontrar a licença **Microsoft 365 Sistema de Telefonia – Usuário Virtual.** Selecione **Detalhes** **e,** em seguida, Comprar .
4. Na página de compra de licença, selecione o número de licenças de usuário virtual que você deseja. Você precisa de uma licença virtual para cada atendimento automático e fila de chamada que planeja configurar. Recomendamos selecionar pelo menos cinco licenças para que você possa facilmente configurar mais atendimentos automáticos e filas de chamada no futuro sem precisar comprar mais licenças imediatamente.
5. **Desmarque Atribuir automaticamente a todos os seus usuários sem licenças**.
6. Selecione **Check-out agora**.
7. Confirme seu pedido, selecione **Próximo** e, em **seguida, Coloque o pedido**.

> [!NOTE]
> Lembre-se de que você ainda deve  **Comprar** a licença mesmo que ela tenha um custo zero.

## <a name="create-a-resource-account"></a>Criar uma conta de recurso

Depois de receber sua Microsoft 365 Sistema de Telefonia *- Licença de Usuário Virtual,* você pode criar sua conta de recurso.

![Captura de tela da interface do usuário adicionar conta de recurso](../media/resource-account-add.png)

1. No centro Teams de administração, expanda **as** configurações de toda a organização e clique em **Contas de recursos.**
2. Selecione **Adicionar**.
3. No painel **Adicionar conta de** recurso, preencha Nome **de** exibição e, em seguida, Nome de **usuário**. Escolha um nome de exibição descritivo, como "Atendimento automático de linha principal" para descrever a finalidade da conta de recurso.
4. Em **Tipo de conta de recurso,** selecione Atendimento **automático**.
5. Selecione **Salvar**.

![Captura de tela de uma lista de contas de recursos](../media/resource-accounts-page.png)

## <a name="assign-a-license"></a>Atribuir uma licença

Depois de criar sua conta de recurso, você precisará atribuir uma Microsoft 365 Sistema de Telefonia *- licença* de usuário virtual *ou* Sistema de Telefonia licença.

![Captura de tela da interface do usuário atribuir licenças no Microsoft 365 de administração](../media/resource-account-assign-virtual-user-license.png)

1. No centro Microsoft 365 de administração, vá para **Usuários**  >  **Usuários ativos.**
2. Selecione sua conta de recurso.
1. Na guia **Licenças e Aplicativos,** em **Licenças,** selecione **Microsoft 365 Sistema de Telefonia - Usuário Virtual**.
1. Selecione **Salvar alterações** e, em **seguida, Fechar**.

## <a name="assign-a-service-number"></a>Atribuir um número de serviço

![Captura de tela da interface do usuário atribuir número de serviço](../media/resource-account-assign-phone-number.png)

1. No centro Teams de administração, acesse **Configurações** em toda a organização e contas **de recurso.** 
1. Selecione a conta de recurso que você acabou de criar e clique em **Atribuir/desatribuição.**
1. Na lista **Telefone de tipos de número,** escolha **Online**.
1. Na caixa **Número de telefone atribuído,** pesquise o número que deseja usar e clique em **Adicionar**. Certifique-se de incluir o código do país (por exemplo, **+1** 250 555 0012)
1. Clique em **Salvar**.
    > [!NOTE]
    > Você não precisa selecionar um assistente automático em Atribuir **a** porque o atendimento automático ao que você deseja adicionar o número já está selecionado.

> [!div class="nextstepaction"]
> [Próxima etapa: Atribuir números de telefone aos usuários](set-up-assign-numbers.md)
