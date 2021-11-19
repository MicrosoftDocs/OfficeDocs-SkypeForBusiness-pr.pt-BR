---
title: Configurar o operador Conexão
author: cazawideh
ms.author: czawideh
manager: serdars
ms.date: 09/30/2021
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: Saiba mais sobre como configurar o operador Conexão.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2fa7a7c314fe2d31e5306ec96902f8ca87e44355
ms.sourcegitcommit: 5c88a07f07f9faad294d614d507e43173efc5f46
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/19/2021
ms.locfileid: "61111961"
---
# <a name="configure-operator-connect"></a>Configurar o operador Conexão

Este artigo descreve como configurar o operador Conexão. Antes de configurar o Conexão, leia [Plan for Operator Conexão](operator-connect-plan.md) para obter informações sobre pré-requisitos e licenciamento.

## <a name="enable-an-operator"></a>Habilitar um operador

Você pode habilitar, editar e remover operadores no Teams de administração. No painel de navegação esquerdo, vá para **Voice > Operators**.

Para habilitar um operador:

1. **Escolha um operador.** Na guia **Todos os operadores,** filtre operadores disponíveis por região ou serviço para encontrar o operador certo para suas necessidades de voz. Em seguida, selecione o operador que você deseja habilitar.  

2. **Selecione países.** Em **Configurações de operador**, selecione os países que você deseja habilitar com o operador selecionado.

3. **Fornecer informações de contato** Suas informações de contato, incluindo seu nome completo e endereço de email, serão compartilhadas automaticamente com sua operadora. Você pode alterar essas informações mais tarde. Além disso, você precisará fornecer o tamanho da empresa e terá a opção de fornecer seu número de telefone. Os operadores usarão essas informações para entrar em contato com você com mais detalhes sobre o operador Conexão.

4. Aceite o aviso de transferência de dados.

5. **Adicione seu operador.** Selecione **Adicionar como meu operador** para salvar.

## <a name="set-up-phone-numbers"></a>Configurar números de telefone

A configuração dos números de telefone depende da configuração de números para novos usuários ou da movimentação de números existentes dos Planos de Chamadas da Microsoft ou do Roteamento Direto.

- Se você precisar adquirir números de telefone para novos usuários, consulte [Adquirir números para novos](#acquire-numbers-for-new-teams-users)Teams usuários .

- Se você quiser mover números existentes de Planos de Chamada para Operador Conexão, consulte Mover números de Planos de Chamada para [Operador Conexão](#move-numbers-from-calling-plans-to-operator-connect).

- Se você quiser mover números existentes do Roteamento Direto para o Conexão operador, consulte Mover números de Roteamento Direto para [Operador Conexão](#move-numbers-from-direct-routing-to-operator-connect).

### <a name="acquire-numbers-for-new-teams-users"></a>Adquirir números para novos Teams usuários

Para adquirir números para novos Teams usuários, siga estas etapas:

1. **Atribuir uma Sistema de Telefonia de usuário.** Você pode atribuir uma Sistema de Telefonia aos usuários do Centro de administração do Microsoft 365 ou usando o PowerShell. Para obter mais informações, [consulte Assign Teams add-on licenses to users](teams-add-on-licensing/assign-teams-add-on-licenses.md).

2. Os usuários que receberão números de telefone adquiridos com o operador Conexão precisam estar no modo TeamsOnly. Se sua organização estiver no modo TeamsOnly, todos os usuários estão no modo TeamsOnly. Para verificar isso, no centro de administração Teams, acesse **Teams > Teams configurações de atualização.** Se sua organização estiver no modo Ilhas, verifique se usuários específicos estão no modo TeamsOnly. Vá para **Usuários** e selecione uma conta de usuário. Na guia **Conta,** em **Teams atualização,** o modo de coexistência deve ser definido como 'TeamsOnly'.

3. **Adquirir números.** Acesse o site da sua operadora para solicitar e adquirir números de telefone. Para uma lista de sites de operador, acesse o diretório Microsoft 365 [Operator Conexão.](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory) Você precisará fornecer sua ID de locatário. Se você não conhece sua ID de locatário, consulte Encontre sua ID Microsoft 365 [locatário](/onedrive/find-your-office-365-tenant-id) para obter mais informações.

4. **Atribuir números.** Depois que o operador concluir o pedido, ele carregará números no locatário. Você pode exibir os números e o provedor no centro de administração Teams, indo para **Voz > Telefone números**. Atribua números aos usuários do Teams de administração ou usando o PowerShell. Para obter mais informações, consulte [Atribuir números](#assign-numbers).

> [!NOTE]
> Além de obter números de telefone para seus [usuários,](getting-phone-numbers-for-your-users.md)você pode obter números de telefone gratuitos ou de chamada gratuita para serviços como Audioconferência (para pontes de conferência), Atendimentos Automáticos e Filas de Chamadas (também chamados de números de serviço). Os números telefônicos de serviço têm uma capacidade de chamada simultânea maior do que números de usuários ou assinantes. Por exemplo, um número de serviço pode manipular centenas de chamadas simultaneamente, enquanto o número de telefone de um usuário só pode manipular algumas chamadas simultaneamente. Para obter números de serviço, entre em contato com sua operadora.

### <a name="emergency-addresses"></a>Endereços de emergência

O endereço de emergência é um local estático associado a um número. Depois de criar endereços de emergência no centro de administração Teams, como você atribui os endereços ou os altera mais tarde, dependerá do operador.

Para atribuir números a endereços de emergência, sua operadora implementará um dos três cenários:

- O operador atribui endereços de emergência aos números de telefone e permite alterá-los posteriormente no Teams de administração.

- O operador não atribui endereços e permite que você atribua endereços de emergência aos números de telefone no Teams de administração.

- O operador atribui endereços de emergência aos números de telefone e não permite alterá-los. Nesse cenário, você precisará entrar em contato com sua operadora para fazer alterações nos números de telefone e no endereço de emergência atribuído.

Para obter mais informações sobre a chamada de emergência, consulte [Manage emergency calling](what-are-emergency-locations-addresses-and-call-routing.md) and Plan and configure dynamic emergency [calling](configure-dynamic-emergency-calling.md).

### <a name="move-numbers-from-calling-plans-to-operator-connect"></a>Mover números de Planos de Chamada para Operador Conexão

1. Entre em contato com seu operador para por seus números para Operador Conexão. Consulte [Microsoft 365 diretório Conexão operador para](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory) encontrar o site da sua operadora.

2. Depois que o operador concluir a ordem de portação, você poderá desatar os números de telefone do Plano de Chamadas dos usuários e remover a Licença do Plano de Chamadas. Em seguida, seu operador pode carregar os números em seu locatário.

3. Atribua números Conexão operador aos usuários usando o centro de administração Teams ou usando o PowerShell. Para obter mais informações, consulte [Atribuir números](#assign-numbers).

### <a name="move-numbers-from-direct-routing-to-operator-connect"></a>Mover números de Roteamento Direto para Operador Conexão

1. Remova o número de telefone existente do usuário da seguinte forma:  

   Obter o URI de linha on-prem existente executando o seguinte comando do PowerShell:

   ```
   Get-CsOnlineUser -Identity <user> | select OnPremLineURI 
   ```

   Remova o URI on-prem Line executando o seguinte comando do PowerShell:  

   ```
   Set-CsUser -Identity <user> -OnPremLineURI $null 
   ```

2. Remova qualquer PSTNUsage associado aos seus usuários, caso contrário, as chamadas serão roteadas para o gateway especificado no Uso de PSTN. Para saber como remover o uso de PSTN, consulte [Set-CsOnlinePstnUsage](/powershell/module/skype/set-csonlinepstnusage?view=skype-ps).

3. Acesse o site da sua operadora para solicitar e adquirir números de telefone. Para encontrar seu site de operadores, consulte o diretório [Microsoft 365 Operador Conexão .](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory) Você precisará fornecer sua ID de locatário. Se você não conhece sua ID de locatário, consulte Encontre sua ID Microsoft 365 [locatário](/onedrive/find-your-office-365-tenant-id) para obter mais informações.

4. Depois que o operador concluir o pedido, ele carregará números no locatário. Você pode exibir os números e o provedor no centro de administração Teams, indo para **Voz > Telefone números**. Atribua números Conexão operador aos usuários usando o centro de administração Teams ou usando o PowerShell. Para obter mais informações, consulte [Atribuir números](#assign-numbers).

### <a name="assign-numbers"></a>Atribuir números

Para obter informações sobre como atribuir números de telefone aos usuários, consulte [Atribuir, alterar](assign-change-or-remove-a-phone-number-for-a-user.md)ou remover um número de telefone para um usuário .

## <a name="manage-your-operators"></a>Gerenciar seus operadores

Na guia **Meus operadores,** você pode exibir seus operadores e seu status e fazer as seguintes alterações em suas seleções:  

- Gerenciar serviços de operador por país
- Suspender um operador
- Remover um operador

> [!NOTE]
> Antes de remover um operador de sua organização ou de um país, você deve remover todos os números de telefone atribuídos aos usuários na organização ou país e entrar em contato com a operadora para liberar os números.

## <a name="release-numbers"></a>Números de versão

Para liberar números de telefone do Teams de administração, vá para a página Telefone **números** e selecione um número.

- Se o número de telefone não for atribuído a um usuário, selecione **Liberar**.

- Se o número de telefone for atribuído a um usuário, você precisará desaignar o número. Selecione **Editar**, em **seguida, Remover usuário**. Depois de salvar suas alterações, selecione **Liberar**.

## <a name="related-topics"></a>Tópicos relacionados

- [Planejar Teams atendimentos automáticos e filas de chamada](plan-auto-attendant-call-queue.md)
