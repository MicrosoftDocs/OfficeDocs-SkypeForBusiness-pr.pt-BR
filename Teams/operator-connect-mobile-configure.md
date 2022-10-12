---
title: Configurar o Teams Phone Mobile
author: CarolynRowe
ms.author: crowe
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
description: Saiba mais sobre como configurar o Teams Phone Mobile.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: e3e0e5c349610e9f8ad73b9b7a50b4c219304ea4
ms.sourcegitcommit: 179713dd2b22736c0d63060a6351eb69ec4abff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/12/2022
ms.locfileid: "68551675"
---
# <a name="configure-teams-phone-mobile"></a>Configurar o Teams Phone Mobile

Para obter uma lista de operadores que participam do programa Telefonia do Microsoft Teams Mobile e os países ou regiões em que o serviço está disponível, consulte [o Microsoft 365 Teams Phone Mobile](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/connect-mobile).

Este artigo descreve como configurar o Teams Phone Mobile. Antes de configurar o Teams Phone Mobile, não se esqueça de ler o [Plano para o Teams Phone Mobile](operator-connect-mobile-plan.md) para obter informações sobre benefícios, pré-requisitos e licenciamento.

## <a name="enable-an-operator"></a>Habilitar um operador

Você pode habilitar, editar e remover operadores no centro de administração do Teams. No painel de navegação esquerdo, vá para **Operadores de > Voz**.

Para habilitar um operador:

1. Escolha um operador que dê suporte ao Teams Phone Mobile. Na guia **Todos os operadores** , filtre os operadores disponíveis por região ou serviço para encontrar o operador certo que dá suporte ao Teams Phone Mobile. Em seguida, selecione o operador que você deseja habilitar.

2. Em **Configurações do operador**, selecione os países que você deseja habilitar com o operador selecionado.

3. **Forneça informações de contato.** Suas informações de contato, incluindo seu nome completo e endereço de email, serão compartilhadas automaticamente com seu operador. Você pode alterar essas informações mais tarde. Além disso, você precisará fornecer o tamanho da empresa e terá a opção de fornecer seu número de telefone. Os operadores usarão essas informações para entrar em contato com você com mais detalhes sobre o Teams Phone Mobile.

4. Aceite o aviso de transferência de dados.

5. Selecione **Adicionar como meu operador** para salvar.

## <a name="set-up-phone-numbers"></a>Configurar números de telefone

Se você quiser adicionar números de telefone habilitados para SIM pagos da sua empresa existente ao Teams, entre em contato com sua operadora para garantir que você tenha a assinatura qualificada do Teams Phone Mobile e que eles possam carregar seus números no Teams. Depois que o operador concluir o pedido, você poderá atribuir esses números aos usuários. 

Para encontrar o site da sua operadora, consulte o [diretório Microsoft 365 Teams Phone Mobile](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory).

Você precisará fornecer sua ID de locatário. Se você não souber sua ID de locatário, consulte [Localizar sua ID de locatário do Microsoft 365](/onedrive/find-your-office-365-tenant-id.md). Você pode estar portando um número de telefone de mesa ou um número de linha de mesa existente para uma assinatura de voz sem fio se ele tiver suporte em sua região e por seu operador. 

A maneira como você configura números de telefone depende se você está configurando números para novos usuários ou movendo números existentes dos Planos de Chamadas da Microsoft, do Operator Connect ou do Roteamento Direto.

- [Adquirir números para novos usuários do Teams](#acquire-numbers-for-new-teams-users).  

- [Mover números dos Planos de Chamadas para o Telefone Móvel do Teams](#move-numbers-from-calling-plans-to-teams-phone-mobile).  

- [Mover números do Operador Conectar-se ao Telefone Móvel do Teams](#move-numbers-from-operator-connect-to-teams-phone-mobile).  

- [Mover números do Roteamento Direto para o Telefone Móvel do Teams](#move-numbers-from-direct-routing-to-teams-phone-mobile).  


### <a name="assign-numbers-to-emergency-addresses"></a>Atribuir números a endereços de emergência

O endereço de emergência é um local estático associado a um número quando acessível por meio de clientes/pontos de extremidade do Microsoft Teams. Depois de criar endereços de emergência no centro de administração do Teams, a forma como você atribui os endereços ou os altera mais tarde dependerá do operador.

Para atribuir números a endereços de emergência que estão sendo usados pelos pontos de extremidade do Microsoft Teams, seu operador implementará um dos três cenários:

- O operador atribui endereços de emergência aos números de telefone e permite alterá-los posteriormente no centro de administração do Teams.

- O operador não atribui endereços e permite que você atribua endereços de emergência aos números de telefone no centro de administração do Teams.

- O operador atribui endereços de emergência aos números de telefone e não permite alterá-los. Nesse cenário, você precisará entrar em contato com sua operadora para fazer alterações nos números de telefone e no endereço de emergência atribuído.

Quando as chamadas são feitas por meio do discador nativo do smartphone habilitado para SIM, o operador pode usar as coordenadas geográficas ou a torre de células que manipulam a chamada para o local de emergência aproximado para obter assistência.

Para obter mais informações sobre chamadas de emergência, consulte [Gerenciar chamadas de](what-are-emergency-locations-addresses-and-call-routing.md) emergência e [planejar e configurar chamadas de emergência dinâmicas](configure-dynamic-emergency-calling.md).

### <a name="acquire-numbers-for-new-teams-users"></a>Adquirir números para novos usuários do Teams

Para adquirir números para novos usuários do Teams, siga estas etapas:

1. **Atribua uma licença do Sistema de Telefonia e uma licença de complemento do Teams Phone Mobile.** Você pode atribuir uma licença do Sistema de Telefonia e uma licença de complemento do Teams Phone Mobile aos usuários do Centro de administração do Microsoft 365 ou usando o PowerShell. Para obter mais informações, [consulte Atribuir licenças de complemento do Teams aos usuários](teams-add-on-licensing/assign-teams-add-on-licenses.md).

2. **Os usuários que receberão números de telefone adquiridos com o Teams Phone Mobile precisam estar no modo TeamsOnly.** Se sua organização estiver no modo TeamsOnly, todos os usuários estão no modo TeamsOnly. 

   Para verificar, no centro de administração do Teams, acesse as configurações **de atualização do Teams > Teams**. Se sua organização estiver no modo Ilhas, verifique se usuários específicos estão no modo TeamsOnly. Vá para **Usuários** e selecione uma conta de usuário. Na guia **Conta** , em **Atualização do Teams,** o modo de coexistência deve ser definido como TeamsOnly.

3. **Adquirir números.** Acesse o site da sua operadora ou entre em contato com eles para solicitar e adquirir números de telefone habilitados para SIM móvel com o serviço Telefone Celular do Teams habilitado. 

   Depois que o operador concluir o pedido, ele carregará números de celular habilitados para SIM para seu locatário. Você pode exibir os números e o provedor no centro de administração do Teams, indo para **Voz > Números de Telefone**. 

4. **Atribuir números.** Você pode atribuir números a usuários do centro de administração do Teams ou usando o PowerShell. Para obter mais informações, consulte [Atribuir números](assign-change-or-remove-a-phone-number-for-a-user.md).

### <a name="move-numbers-from-calling-plans-to-teams-phone-mobile"></a>Mover números dos Planos de Chamadas para o Telefone Móvel do Teams

1. Verifique se você tem assinaturas qualificadas do Microsoft 365 para o Teams Phone Mobile e a licença de complemento do Teams Phone Mobile. Você precisa remover [o número de telefone a ser movido para os respectivos usuários](assign-change-or-remove-a-phone-number-for-a-user.md#remove-a-phone-number-from-a-user). 

2. Entre em contato com seu operador para portar seus números para o Teams Phone Mobile em um plano de voz sem fio qualificado habilitado para SIM. 

3. Depois que o operador concluir a ordem de portabilidade, o operador carregará os números em seu locatário.  Você pode exibir os números e o provedor no centro de administração do Teams, indo para **Voz > Números de Telefone**. 

4. Você pode atribuir números aos usuários usando o centro de administração do Teams ou usando o PowerShell. Para obter mais informações, consulte [Atribuir números](assign-change-or-remove-a-phone-number-for-a-user.md).

### <a name="move-numbers-from-operator-connect-to-teams-phone-mobile"></a>Mover números do Operador Conectar-se ao Telefone Móvel do Teams

1. Verifique se você tem assinaturas qualificadas do Microsoft 365 para o Teams Phone Mobile e a licença de complemento do Teams Phone Mobile. Você precisa remover [o número de telefone a ser movido para os respectivos usuários](assign-change-or-remove-a-phone-number-for-a-user.md#remove-a-phone-number-from-a-user). Entre em contato com seu provedor de Conexão de Operador existente para remover os números de telefone do seu locatário.

2. Entre em contato com seu operador para portar seus números para o Teams Phone Mobile em um plano de voz sem fio qualificado habilitado para SIM. 

3. Depois que o operador concluir a ordem de portabilidade, o operador carregará os números em seu locatário. Você pode exibir os números e o provedor no centro de administração do Teams, indo para **Voz > Números de Telefone**. 

4. Você pode atribuir números aos usuários usando o centro de administração do Teams ou usando o PowerShell. Para obter mais informações, consulte [Atribuir números](assign-change-or-remove-a-phone-number-for-a-user.md).

### <a name="move-numbers-from-direct-routing-to-teams-phone-mobile"></a>Mover números do Roteamento Direto para o Telefone Móvel do Teams   

Para mover números do Roteamento Direto para o Teams Phone Mobile, você precisará concluir as seguintes etapas:

1. [Determine se os números de Roteamento Direto existentes são atribuídos online ou localmente](#determine-if-the-existing-direct-routing-numbers-are-assigned-online-or-on-premises).

2. [Migre os números do Roteamento Direto para o Teams Phone Mobile](#migrate-the-numbers-from-direct-routing-to-teams-phone-mobile).

2. [Remova a política de roteamento de voz online associada ao seu usuário](#remove-the-online-voice-routing-policy-associated-with-your-user).

3. [Adquirir números de telefone](#acquire-phone-numbers).

4. [Atribua números de telefone](#assign-phone-numbers).

Essas etapas são descritas com mais detalhes nas seções a seguir.

#### <a name="determine-if-the-existing-direct-routing-numbers-are-assigned-online-or-on-premises"></a>Determine se os números de Roteamento Direto existentes são atribuídos online ou localmente.

A maneira como você remove os números de Roteamento Direto existentes depende se o número é atribuído localmente ou online.

1. Primeiro, verifique se o usuário recebe um número de Roteamento Direto executando o comando do PowerShell do Teams a seguir. NumberType deve ser DirectRouting:

   ```PowerShell
   Get-CsPhoneNumberAssignment -AssignedPstnTargetId <user> 
   ```

2. Determine se o número é atribuído online ou localmente executando o seguinte comando do PowerShell do Teams:

   ```PowerShell
   Get-CsOnlineUser -Identity <user> | fl RegistrarPool, OnPremLineURI, LineURI 
   ```

   Se OnPremLineUri for preenchido com um número de telefone E.164, o número de telefone foi atribuído localmente e sincronizado com o Microsoft 365.

#### <a name="migrate-the-numbers-from-direct-routing-to-teams-phone-mobile"></a>Migrar os números do Roteamento Direto para o Telefone Móvel do Teams

Para migrar números, siga as etapas abaixo.  

> [!Important]
> Durante a migração, o número de telefone estará fora de serviço. Coordem com a operadora do Teams Phone Mobile antes de iniciar a migração.

- **Para migrar os números de Roteamento Direto existentes atribuídos online ao Teams Phone Mobile**, entre em contato com sua operadora. Para localizar o site da sua operadora, consulte o [diretório Microsoft 365 Teams Phone Mobile](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory). Na data e hora acordados, seu operador migrará seus números do Roteamento Direto para o Telefone Móvel do Teams. Isso pode envolver a remoção do número de telefone que está sendo migrado do seu locatário e adicioná-lo novamente como um novo número de telefone associado ao Teams Phone Mobile.

- **Para migrar números de Roteamento Direto atribuídos localmente para o Teams Phone Mobile**, execute o seguinte comando Skype for Business Server PowerShell:

   ```PowerShell
   Set-CsUser -Identity <user> -LineURI $null 
   ```
  Para verificar se o número local foi removido e se as alterações foram sincronizadas do local para o Microsoft 365, execute o seguinte comando do PowerShell do Teams:

   ```PowerShell
   Get-CsOnlineUser -Identity <user> | fl RegistrarPool, OnPremLineURI, LineURI 
   ```

Depois que as alterações forem sincronizadas com o diretório online do Microsoft 365, a saída esperada será:

```
ConsoleCopy
RegistrarPool                        : pool.infra.lync.com
OnPremLineURI                        : 
LineURI                              
```

Para verificar se o número de telefone foi removido, execute o seguinte comando do PowerShell do Teams:

```PowerShell
Get-CsOnlineUser -Identity <user> | fl LineUri
```

> [!NOTE]
> O tempo necessário para que a remoção entre em vigor depende da sua configuração. A remoção do número de telefone pode levar até 10 minutos, em casos raros, pode levar até 24 horas. 

#### <a name="remove-the-online-voice-routing-policy-associated-with-your-user"></a>Remover a política de roteamento de voz online associada ao seu usuário

Depois que o número não for atribuído, remova a política de roteamento de voz online associada ao usuário executando o seguinte comando do PowerShell do Teams:

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity <user> -PolicyName $Null
```

#### <a name="acquire-phone-numbers"></a>Adquirir números de telefone

Entre em contato com seu operador para portar seus números para o Teams Phone Mobile em um plano de voz sem fio qualificado habilitado para SIM.

Depois que o operador concluir o pedido, ele carregará números em seu locatário. Você pode exibir os números e o provedor no centro de administração do Teams, indo para **Voz > Números de Telefone**. 

#### <a name="assign-phone-numbers"></a>Atribuir números de telefone

Você pode atribuir números do Teams Phone Mobile aos usuários usando o centro de administração do Teams ou usando o PowerShell. Para obter mais informações, consulte [Atribuir números](assign-change-or-remove-a-phone-number-for-a-user.md).


## <a name="manage-your-operators"></a>Gerenciar seus operadores

Na guia **Meus operadores** , você pode exibir seus operadores e seu status e fazer as seguintes alterações em suas seleções:  

- Gerenciar serviços de operador por país
- Suspender um operador
- Remover um operador

> [!NOTE]
> Antes de remover um operador de sua organização ou de um país, você deve remover todos os números de telefone atribuídos aos usuários na organização ou no país e entrar em contato com o operador para liberar os números.

## <a name="release-numbers"></a>Números de versão

Para liberar números de telefone do Centro de administração do Teams, vá para a página **Números de** telefone e selecione um número.

- Se o número de telefone não estiver atribuído a um usuário, selecione **Liberar**.

- Se o número de telefone for atribuído a um usuário, você precisará cancelar a atribuição do número. Selecione **Editar** e, **em seguida, Remover usuário**. Depois de salvar as alterações, selecione **Liberar**.

## <a name="manage-user-incoming-calling-policies"></a>Gerenciar políticas de chamada de entrada do usuário

Você pode gerenciar as políticas de chamadas de entrada de um usuário usando o centro de administração do Teams ou usando o PowerShell. Por padrão, chamadas de entrada para usuários do Teams Phone Mobile tocarão primeiro no aplicativo Teams no dispositivo móvel habilitado para SIM do usuário. 

- Se a preferência de chamada de entrada de um usuário for definida como o aplicativo Teams, todas as chamadas de entrada tocarão no aplicativo Teams no smartphone habilitado para SIM e em qualquer outro ponto de extremidade do Teams em outros dispositivos simultaneamente. 

- Se a preferência de chamada de entrada de um usuário for definida como o discador nativo, todas as chamadas de entrada tocarão no discador nativo no smartphone habilitado para SIM e tocarão simultaneamente em todos os outros pontos de extremidade do Teams em outros dispositivos. 

### <a name="use-the-teams-admin-center"></a>Usar o centro de administração do Teams

Para gerenciar as políticas de chamadas de entrada de um usuário usando o Centro de administração do Teams:

1. Na guia voz, selecione **Políticas de Mobilidade**. 

2. Para adicionar uma nova política móvel, clique em **Adicionar**.

3. Selecione um nome, adicione uma descrição da política e escolha um dos seguintes na opção suspensa Selecionar um **discador** móvel:

   -  **O Microsoft Teams** tocará primeiro no aplicativo Teams no smartphone habilitado para SIM. 

   - **O Discador Nativo** para tocar o Discador Nativo no smartphone habilitado para SIM primeiro.

4. Atribua as políticas aos usuários. Consulte [Atribuir políticas](assign-policies-users-and-groups.md).


### <a name="use-powershell"></a>Usar o PowerShell

1. Conecte-se ao seu locatário: Connect-MicrosoftTeams.
 
2. Crie políticas para chamadas de entrada para tocar primeiro no discador nativo ou no aplicativo Teams. (Você pode escolher o nome da política; este exemplo usa TeamsFirst e NativeFirst.) 

   ```PowerShell
   New-CsTeamsMobilityPolicy -identity TeamsFirst -MobileDialerPreference Teams 
   New-CsTeamsMobilityPolicy -identity NativeFirst -MobileDialerPreference Native 
   ```

3. Conceder políticas aos usuários: 

   ```PowerShell
   Grant-CsTeamsMobilityPolicy NativeFirst -Identity user@xyz.onmicrosoft.com
   Grant-CsTeamsMobilityPolicy TeamsFirst -Identity user@xyz.onmicrosoft.com
   ```

4. Verifique as políticas de usuário: 

   ```PowerShell
   get-CsUserpolicyassignment -identity user@xyz.onmicrosoft.com
   ```
 
 5. Verifique todas as opções de política de mobilidade: 
    
    ```PowerShell
    Get-CsTeamsMobilityPolicy
    ```  

 








