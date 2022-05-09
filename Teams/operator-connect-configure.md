---
title: Configurar Conexão do operador
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
description: Saiba mais sobre como configurar o Conexão do operador.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 222ea1852ef4336c21cfb24c977c20665a667ff3
ms.sourcegitcommit: 9968ef7d58c526e35cb58174db3535fd6b2bd1db
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/09/2022
ms.locfileid: "65284066"
---
# <a name="configure-operator-connect"></a>Configurar Conexão do operador

Este artigo descreve como configurar o Conexão do operador. Antes de configurar Conexão do operador, leia [Plan for Conexão do operador](operator-connect-plan.md) para obter informações sobre pré-requisitos e licenciamento.

## <a name="enable-an-operator"></a>Habilitar um operador

Você pode habilitar, editar e remover operadores no Teams de administração. No painel de navegação esquerdo, vá para **Operadores de > Voz**.

Para habilitar um operador:

1. **Escolha um operador.** Na guia **Todos os operadores** , filtre os operadores disponíveis por região ou serviço para encontrar o operador certo para suas necessidades de voz. Em seguida, selecione o operador que você deseja habilitar.  

2. **Selecionar países.** Em **Configurações do operador**, selecione os países que você deseja habilitar com o operador selecionado.

3. **Fornecer informações de contato** Suas informações de contato, incluindo seu nome completo e endereço de email, serão compartilhadas automaticamente com seu operador. Você pode alterar essas informações mais tarde. Além disso, você precisará fornecer o tamanho da empresa e terá a opção de fornecer seu número de telefone. Os operadores usarão essas informações para entrar em contato com você com mais detalhes sobre Conexão do operador.

4. Aceite o aviso de transferência de dados.

5. **Adicione seu operador.** Selecione **Adicionar como meu operador** para salvar.

## <a name="set-up-phone-numbers"></a>Configurar números de telefone

A maneira como você configura números de telefone depende se você está configurando números para novos usuários ou movendo números existentes dos Planos de Chamadas da Microsoft ou do Roteamento Direto.

- Se você precisar adquirir números de telefone para novos usuários, consulte [Adquirir números para novos Teams usuários](#acquire-numbers-for-new-teams-users).

- Se você quiser mover números existentes de Planos de Chamadas para Conexão do operador, consulte [Mover](#move-numbers-from-calling-plans-to-operator-connect) números de Planos de Chamadas para Conexão do operador.

- Se você quiser mover números existentes do Roteamento Direto para Conexão do operador, consulte Mover números do Roteamento Direto para o [Conexão do operador](#move-numbers-from-direct-routing-to-operator-connect).

### <a name="acquire-numbers-for-new-teams-users"></a>Adquirir números para novos Teams usuários

Para adquirir números para novos Teams novos usuários, siga estas etapas:

1. **Atribuir uma licença Sistema de Telefonia usuário.** Você pode atribuir uma Sistema de Telefonia aos usuários do Centro de administração do Microsoft 365 ou usando o PowerShell. Para obter mais informações, [consulte Atribuir Teams licenças de complemento aos usuários](teams-add-on-licensing/assign-teams-add-on-licenses.md).

2. Os usuários que receberão números de telefone adquiridos com Conexão do operador precisam estar no modo TeamsOnly. Se sua organização estiver no modo TeamsOnly, todos os usuários estão no modo TeamsOnly. Para verificar isso, no centro Teams administrador, vá **para Teams > Teams configurações de atualização**. Se sua organização estiver no modo Ilhas, verifique se usuários específicos estão no modo TeamsOnly. Vá para **Usuários** e selecione uma conta de usuário. Na guia **Conta**, em **Teams atualização,** o modo de coexistência deve ser definido como 'TeamsOnly'.

3. **Adquirir números.** Acesse o site da sua operadora para solicitar e adquirir números de telefone. Para obter uma lista de sites de operadores, vá para o [Microsoft 365 Conexão do operador diretório](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory). Você precisará fornecer sua ID de locatário. Se você não souber sua ID de locatário, consulte [Localizar sua ID Microsoft 365 locatário](/onedrive/find-your-office-365-tenant-id) para obter mais informações.

4. **Atribuir números.** Depois que o operador concluir o pedido, ele carregará números em seu locatário. Você pode exibir os números e o provedor no centro de Teams de administração, indo para **Voz > Telefone números**. Atribua números aos usuários do Teams de administração ou usando o PowerShell. Para obter mais informações, consulte [Atribuir números](#assign-numbers).

> [!NOTE]
> Além de esquecer os números de telefone para seus  [usuários, você](getting-phone-numbers-for-your-users.md) pode obter números de telefone de chamada tarifada ou gratuita para serviços como Audioconferência (para pontes de conferência), Atendedores Automáticos e Filas de Chamadas (também chamados de números de serviço). Os números telefônicos de serviço têm uma capacidade de chamada simultânea maior do que números de usuários ou assinantes. Por exemplo, um número de serviço pode lidar com centenas de chamadas simultaneamente, enquanto o número de telefone de um usuário só pode manipular algumas chamadas simultaneamente. Para obter números de serviço, entre em contato com seu operador.

### <a name="emergency-addresses"></a>Endereços de emergência

O endereço de emergência é um local estático associado a um número. Depois de criar endereços de emergência no Teams de administração, a forma como você atribui os endereços ou os altera mais tarde dependerá do operador.

Para atribuir números a endereços de emergência, o operador implementará um dos três cenários:

- O operador atribui endereços de emergência aos números de telefone e permite alterá-los posteriormente no Teams de administração.

- O operador não atribui endereços e permite que você atribua endereços de emergência aos números de telefone no centro Teams administrador.

- O operador atribui endereços de emergência aos números de telefone e não permite alterá-los. Nesse cenário, você precisará entrar em contato com sua operadora para fazer alterações nos números de telefone e no endereço de emergência atribuído.

Para obter mais informações sobre chamadas de emergência, consulte [Gerenciar chamadas de](what-are-emergency-locations-addresses-and-call-routing.md) emergência e [planejar e configurar chamadas de emergência dinâmicas](configure-dynamic-emergency-calling.md).

### <a name="move-numbers-from-calling-plans-to-operator-connect"></a>Mover números de Planos de Chamadas para Conexão do operador

1. Entre em contato com o operador para portar seus números para Conexão do operador. Consulte [Microsoft 365 Conexão do operador diretório](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory) para localizar o site da sua operadora.

2. Depois que o operador concluir a ordem de portabilidade, você poderá cancelar a atribuição dos números de telefone do Plano de Chamadas dos usuários e remover a Licença do Plano de Chamadas. Em seguida, o operador pode carregar os números em seu locatário.

3. Atribua Conexão do operador a usuários usando o Teams de administração ou usando o PowerShell. Para obter mais informações, consulte [Atribuir números](#assign-numbers).

### <a name="move-numbers-from-direct-routing-to-operator-connect"></a>Mover números do Roteamento Direto para Conexão do operador

Para mover números do Roteamento Direto para o Conexão do operador, o número de Roteamento Direto existente que foi carregado para seu locatário pelo operador deve ser removido do usuário ao qual ele está atribuído. Em seguida, depois que o número for migrado para Conexão do operador, você poderá atribuir novamente o número ao usuário. Para mudar do Roteamento Direto para Conexão do operador com números de telefone locais ou online, siga as etapas abaixo:

>[!IMPORTANT]
> O número de telefone estará fora de serviço durante a migração, portanto, coordordem com o operador Conexão do operador antes de começar.

#### <a name="step-1---remove-existing-direct-routing-numbers"></a>Etapa 1 – Remover números de Roteamento Direto existentes.

A maneira como você remove os números de Roteamento Direto existentes depende se o número é atribuído localmente ou online. Para verificar, execute o seguinte comando Teams módulo do PowerShell:
    
```PowerShell
Get-CsOnlineUser -Identity <user> | fl RegistrarPool, OnPremLineURI, LineURI 
```

Se `OnPremLineUri` for preenchido com um número de telefone E.164, o número de telefone foi atribuído localmente e sincronizado com Office 365.
    
**Para remover os números de Roteamento Direto atribuídos localmente,** execute o seguinte Skype for Business Server comando do PowerShell:
    
```PowerShell
Set-CsUser -Identity <user> -LineURI $null 
```

O tempo necessário para que a remoção entre em vigor depende da sua configuração. Para verificar se o número local foi removido e se as alterações foram sincronizadas, execute o seguinte comando Teams Módulo do PowerShell: 
    
```PowerShell
Get-CsOnlineUser -Identity <user> | fl RegistrarPool, OnPremLineURI, LineURI 
```
       
Depois que as alterações forem sincronizadas com Office 365 diretório online, a saída esperada será: 
       
 ```console
RegistrarPool                        : pool.infra.lync.com
OnPremLineURI                        : 
LineURI                              : 
```

<br> **Para remover os números de Roteamento Direto online existentes atribuídos online,** execute o seguinte comando Teams módulo do PowerShell:


```PowerShell
Remove-CsPhoneNumberAssignment -Identity <user> -PhoneNumber <pn> -PhoneNumberType DirectRouting
```

A remoção do número de telefone pode levar até 10 minutos. Em casos raros, pode levar até 24 horas. Para verificar se o número de telefone foi removido, execute o seguinte comando Teams módulo do PowerShell: 


```PowerShell
Get-CsOnlineUser -Identity <user> | fl LineUri
```

#### <a name="step-2---remove-the-online-voice-routing-policy-associated-with-your-user"></a>Etapa 2 – Remover a política de roteamento de voz online associada ao seu usuário

Depois que o número não for atribuído, remova a política de roteamento de voz online associada ao usuário executando o seguinte comando Teams módulo do PowerShell:

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity <user> -PolicyName $Null
```

#### <a name="step-3---acquire-phone-numbers"></a>Etapa 3 – Adquirir números de telefone

Acesse o site da sua operadora para solicitar e adquirir números de telefone. Para localizar seu site de operadores, consulte [o Microsoft 365 Conexão do operador diretório](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory). Você precisará fornecer sua ID de locatário. Se você não souber sua ID de locatário, consulte [Localizar sua ID Microsoft 365 locatário](/onedrive/find-your-office-365-tenant-id) para obter mais informações.

#### <a name="step-4---assign-phone-numbers"></a>Etapa 4 – Atribuir números de telefone

Depois que o operador concluir o pedido, ele carregará números em seu locatário. Você pode exibir os números e o provedor no centro de Teams de administração, indo para **Voz > Telefone números**. Atribua Conexão do operador a usuários usando o Teams de administração ou usando o PowerShell. Para obter mais informações, consulte [Atribuir números](#assign-numbers).

### <a name="assign-numbers"></a>Atribuir números

Para obter informações sobre como atribuir números de telefone aos usuários, consulte [Atribuir, alterar ou remover um número de telefone para um usuário](assign-change-or-remove-a-phone-number-for-a-user.md).

## <a name="manage-your-operators"></a>Gerenciar seus operadores

Na guia **Meus operadores** , você pode exibir seus operadores e seu status e fazer as seguintes alterações em suas seleções:  

- Gerenciar serviços de operador por país
- Suspender um operador
- Remover um operador

> [!NOTE]
> Antes de remover um operador de sua organização ou de um país, você deve remover todos os números de telefone atribuídos aos usuários na organização ou no país e entrar em contato com o operador para liberar os números.

## <a name="release-numbers"></a>Números de versão

Para liberar números de telefone do Teams de administração, vá para a página **Telefone números** e selecione um número.

- Se o número de telefone não estiver atribuído a um usuário, selecione **Liberar**.

- Se o número de telefone for atribuído a um usuário, você precisará cancelar a atribuição do número. Selecione **Editar** e, **em seguida, Remover usuário**. Depois de salvar as alterações, selecione **Liberar**.

## <a name="related-topics"></a>Tópicos relacionados

- [Planejar para Teams atendedores automáticos e filas de chamadas](plan-auto-attendant-call-queue.md)
