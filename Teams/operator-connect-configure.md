---
title: Configurar o operador Conexão
author: cazawideh
ms.author: czawideh
manager: serdars
ms.date: 04/12/2021
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
ms.openlocfilehash: e82c862810448552bb9d2dc2d721815b5db43f55
ms.sourcegitcommit: 17e34d2de3d10f1d04929a695e301127db7014bd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2021
ms.locfileid: "52689882"
---
# <a name="configure-operator-connect"></a>Configurar o operador Conexão

>[!NOTE]
>O Conexão de operador está disponível apenas na **visualização pública.** A visualização pública permite testar os recursos futuros e fornecer comentários. Os recursos incluídos na visualização pública podem não estar completos, podem sofrer alterações e não são suportados Office 365 Government Nuvens.

Este artigo descreve como configurar o operador Conexão. Antes de configurar o Conexão, leia [Plan for Operator Conexão](operator-connect-plan.md) para obter informações sobre pré-requisitos e licenciamento.

## <a name="enable-an-operator"></a>Habilitar um operador

Você pode habilitar, editar e remover operadores no Teams Admin Center. No painel de navegação esquerdo, vá para **Voice > Operators**.

Para habilitar um operador:

1. **Escolha um operador.** Na guia **Todos os operadores,** filtre operadores disponíveis por região ou serviço para encontrar o operador certo para suas necessidades de voz. Em seguida, selecione o operador que você deseja habilitar.  

2. **Selecione países.** Em **Configurações de operador**, selecione os países que você deseja habilitar com o operador selecionado.

3. **Forneça informações de contato (opcional).** Se você quiser que os operadores contatem você com informações adicionais sobre o operador Conexão, marque a caixa e forneça suas informações de contato.  

4. **Aceite o aviso de transferência de dados.**

5. **Adicione seu operador.** Selecione **Adicionar como meu operador** para salvar.

## <a name="set-up-phone-numbers"></a>Configurar números de telefone

A configuração dos números de telefone depende da configuração de números para novos usuários ou da movimentação de números existentes dos Planos de Chamadas da Microsoft ou do Roteamento Direto.

- Se você precisar adquirir números de telefone para novos usuários, consulte [Adquirir números para novos](#acquire-numbers-for-new-teams-users)Teams usuários .

- Se você quiser mover números existentes de Planos de Chamada para Operador Conexão, consulte Mover números de Planos de Chamada para [Operador Conexão](#move-numbers-from-calling-plans-to-operator-connect).

- Se você quiser mover números existentes do Roteamento Direto para o Conexão operador, consulte Mover números de Roteamento Direto para [Operador Conexão](#move-numbers-from-direct-routing-to-operator-connect).

>[!IMPORTANT]
>**Endereços de emergência:** Os endereços de emergência associados a um número adquirido do operador são gerenciados diretamente com o operador. Entre em contato com o operador para fazer alterações.

### <a name="acquire-numbers-for-new-teams-users"></a>Adquirir números para novos Teams usuários

Para adquirir números para novos Teams usuários, siga estas etapas:

1. **Atribuir uma Sistema de Telefonia de usuário.** Você pode atribuir uma Sistema de Telefonia a seus usuários a partir do centro de administração Microsoft 365 ou usando o PowerShell. Para obter mais informações, [consulte Assign Teams add-on licenses to users](teams-add-on-licensing/assign-teams-add-on-licenses.md).

2. **Certifique-se de estar no modo TeamsOnly.** Para verificar, no centro de administração Teams, vá para **Configurações** de toda a organização > Teams atualização . O modo de coexistência deve ser definido como Teams somente.

3. **Crie e valide endereços de emergência.** No centro Teams de administração, vá para Locais > **endereços** de emergência para configurar endereços de emergência. Para saber mais, confira [Adicionar, alterar ou remover um local de emergência para sua organização.](add-change-remove-emergency-location-organization.md)

4. **Adquirir números.** Acesse o site da sua operadora para solicitar e adquirir números de telefone. Para ver uma lista de sites de operadores, consulte [Operators](#operators). Você precisará fornecer sua ID de locatário. Se você não conhece sua ID de locatário, consulte Encontre sua ID Microsoft 365 [locatário](/onedrive/find-your-office-365-tenant-id) para obter mais informações.

5. **Atribuir números.** Depois que o operador concluir o pedido, ele carregará números de teste em seu locatário. Você pode exibir os números e o provedor no centro de administração Teams, indo para **Voz > Telefone números**. Atribua números aos usuários usando o Teams de administração ou usando o PowerShell. Para obter mais informações, consulte [Atribuir números](#assign-numbers).
 

### <a name="move-numbers-from-calling-plans-to-operator-connect"></a>Mover números de Planos de Chamada para Operador Conexão

1. Entre em contato com seu operador para por seus números para Operador Conexão. Consulte [Operadores](#operators) para encontrar o site da sua operadora.

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
   Set-CsUser -identity <user> - OnPremLineURI $null 
   ```

2. Remova qualquer PSTNUsage associado aos seus usuários, caso contrário, as chamadas serão roteadas para o gateway especificado no Uso de PSTN. Para saber como remover o uso de PSTN, consulte [Set-CsOnlinePstnUsage](/powershell/module/skype/set-csonlinepstnusage?view=skype-ps).

3. Acesse o site da sua operadora para solicitar e adquirir números de telefone. Para ver uma lista de sites de operadores, consulte [Operators](#operators). Você precisará fornecer sua ID de locatário. Se você não conhece sua ID de locatário, consulte Encontre sua ID Microsoft 365 [locatário](/onedrive/find-your-office-365-tenant-id) para obter mais informações.

4. Depois que o operador concluir o pedido, ele carregará números de teste em seu locatário. Você pode exibir os números e o provedor no centro de administração Teams, indo para **Voz > Telefone números**. Atribua números Conexão operador aos usuários usando o centro de administração Teams ou usando o PowerShell. Para obter mais informações, consulte [Atribuir números](#assign-numbers).

   

### <a name="assign-numbers"></a>Atribuir números

Se você estiver adicionando novos usuários Teams ou movendo usuários existentes para o Conexão operador, as etapas para atribuir números são as seguintes:

Para atribuir números usando o Teams de administração, vá para Telefone **números**. As etapas são as mesmas que atribuir números para Planos de Chamada. Para obter mais informações, [consulte Atribuir um número de telefone a um usuário](assign-change-or-remove-a-phone-number-for-a-user.md).

Para atribuir números usando o PowerShell, use o cmdlet Set-CsOnlineVoiceUser da seguinte forma:

```
Set-CsOnlineVoiceUser -Identity <user>  -TelephoneNumber <phone number> 
```

Por exemplo:

```
Set-CsOnlineVoiceUser -Identity john@contoso.com -TelephoneNumber +14255550101
```

Para obter mais informações sobre como atribuir números de telefone aos seus usuários, consulte [Atribuir, alterar](assign-change-or-remove-a-phone-number-for-a-user.md)ou remover um número de telefone para um usuário .



## <a name="manage-your-operators"></a>Gerenciar seus operadores

Na guia Meus operadores, você pode exibir seus operadores e seu status e fazer as seguintes alterações em suas seleções:  

- Gerenciar serviços de operador por país
- Suspender um operador
- Remover um operador

> [!NOTE]
> Antes de remover um operador de sua organização ou de um país, você deve remover todos os números de telefone atribuídos aos usuários na organização ou país e entrar em contato com a operadora para liberar os números.

## <a name="operators"></a>Operadores

Você pode adquirir números de telefone das seguintes operadoras, indo para os sites vinculados aqui:


|Operador  |Site do operador  |
|---------|---------|
|`BT`     |     https://www.globalservices.bt.com/en/aboutus/operator-connect        |
|`Deutsche Telekom`     |   https://cloud.telekom.de/de/blog/cloud-software/microsoft-teams-operator-connect      |
|`Intrado`     | https://insight.intrado.com/operator-connect       |
|`NTT`     |  https://www.hello.global.ntt/operator-connect       |
|`NuWave`     |   https://ipilot.io/microsoft-operator-connect/   |
|`Orange Business Services`     | https://www.orange-business.com/en/blogs/operator-connect-orange-and-microsoft-streamline-calling-for-teams-users        |
|`Pure IP`    | https://info.pure-ip.com/operator-connect        |
|`Rogers`    | https://www.rogers.com/business/products-and-solutions/microsoft-365-business-voice        |
|`TATA Communications`     |  https://www.tatacommunications.com/solutions/unified-communications/unified-communications-as-a-service/microsoft-teams-solutions/       |
|`Telenor`     | https://www.telenor.no/bedrift/telefoni/teams/operator-connect        |
|`Verizon`     |  https://www.verizon.com/business/resources/lp/operator-connect       |
