---
title: Configurando o suporte de federação para um cliente do Skype for Business Online cliente
ms.reviewer: ''
ms:assetid: e5f7f38d-ede5-4af3-88c2-026e8a78df12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202193(v=OCS.15)
ms:contentKeyID: 48185669
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Se você implantar o Skype para negócios em sua organização, você pode federar os domínios do Skype um ou mais para clientes corporativos on-line. '
ms.openlocfilehash: d829b9688af315cb0d8dd0f143d651035a196417
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33903296"
---
# <a name="configuring-federation-support-for-a-skype-for-business-online-customer-in-skype-for-business-server"></a>Configurando o suporte de federação para um Skype para cliente Business Online no Skype para Business Server 

Você pode fornecer serviços de comunicação aos usuários em sua organização em qualquer uma das seguintes maneiras:

  - Implantando Skype para Business Server em sua organização (conhecido como *Serviços no local*) e a configuração Skype para contas de usuário de negócios em sua organização.
  - Configurando um Skype Microsoft Business Online conta de cliente com um provedor de hospedagem e configurando as contas de usuário com o provedor de hospedagem (conhecido como *serviços online*).

Se você implantar o Skype para negócios em sua organização, você pode federar os domínios do Skype um ou mais para clientes corporativos on-line. Para habilitar a federação entre usuários do Skype seu local para implantação de negócios e de um Skype para cliente Business Online, você deve configurar o suporte para o domínio e os usuários da Skype para cliente Business Online.

> [!NOTE]  
> Esta documentação descreve apenas os procedimentos de configuração de sua organização para oferecer suporte à Federação com um Skype para cliente Business Online. Esta documentação não descreve os procedimentos para configurar o Skype para cliente Business Online oferecer suporte à Federação. 

## <a name="prerequisites-for-federating-with-a-skype-for-business-online-customer"></a>Pré-requisitos para a federação com um Skype para cliente Business Online

Para estabelecer uma federação com um Skype para cliente Business Online, você deve já tenha concluído a implantação inicial e a configuração do Skype para Business Server em sua organização. Isso inclui o seguinte:

  - Implantar pelo menos um servidor Standard Edition ou um pool de Front End do Enterprise Edition em sua organização. 
  - Habilitando contas de usuário interno do Skype para Business Server. 
  - Implantar pelo menos um servidor de borda e outros componentes necessários para dar suporte ao acesso de usuário externo. Para obter detalhes, consulte [Gerenciando federação e acesso externo à Skype para Business Server](../managing-federation-and-external-access.md).
  - Habilitando o suporte de Federação dentro da sua organização e configurando o método apropriado para controlar o acesso por domínios federados. Para obter detalhes, consulte [Habilitar ou desabilitar o acesso de usuário remoto](../access-edge/enable-or-disable-remote-user-access.md) e [Gerenciar SIP federated providers para sua organização](../sip-providers/manage-sip-federated-providers-for-your-organization.md).
  - Permitindo o acesso de usuário externo para usuários em sua organização. Para obter detalhes, consulte [atribuir uma política de acesso de usuário externo para uma Skype para negócios de usuário habilitado](../external-access-policies/assign-an-external-user-access-policy.md).



## <a name="configure-federation-support-for-a-skype-for-business-online-domain"></a>Configurar o suporte de federação para um Skype para domínio Business Online

A federação com um Skype para cliente Business Online requer que você conclua as seguintes etapas:

  - Configure o suporte para o domínio do Skype para 2010 Online de negócios do cliente (por exemplo, contoso.onmicrosoft.com). Conforme especificado na [pré-requisitos para a federação com um Skype para Business Online do cliente](#prerequisites-for-federating-with-a-skype-for-business-online-customer), você deve ter já habilitado a federação para sua organização. Habilitar a federação, é preciso especificar o método a ser usado para controlar o acesso por domínios federados. Se você configurou a sua organização para usar a descoberta, adiciona o domínio à lista de permissões da sua organização é opcional. Se você não habilitou a descoberta de domínio, você deve adicionar o nome de domínio do Skype para cliente Business Online à sua lista de domínios permitidos. Você pode adicionar um nome de domínio usando o Skype para o painel de controle do Business Server ou executando o cmdlet **New-CSAllowedDomain** . Para obter detalhes sobre como usar o Skype para painel de controle do servidor de negócios, incluindo a habilitação da descoberta de domínios, consulte [Gerenciar SIP federated providers para sua organização no Skype para Business Server](../sip-providers/manage-sip-federated-providers-for-your-organization.md). Para obter detalhes sobre como usar o cmdlet **New-CSAllowedDomain** para adicionar um domínio, consulte [New-CsAllowedDomain](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsAllowedDomain).

    > [!NOTE]  
    > Um Skype para cliente Business Online pode ter vários domínios. Se você quiser estabelecer uma federação com mais de um dos domínios, você deve configurar o suporte para cada domínio individual com a qual você deseja oferecer suporte à Federação e o administrador do Skype para cliente Business Online deve habilitar a federação para cada um dos domínios para seja federado.

  - Configure o suporte para o provedor de hospedagem do Skype para domínio Business Online do cliente com o qual você deseja federar. Use o procedimento desta seção para configurar o suporte para o provedor de hospedagem.

    > [!NOTE]  
    > Esta etapa é necessária somente para federação com um domínio de um Skype para cliente Business Online, mas não para federação com qualquer domínio implantado localmente no local do parceiro federado.


### <a name="to-configure-support-for-a-hosting-provider"></a>Configurar o suporte para um provedor de hospedagem

1.  Em um servidor Front-End, inicie o Skype do Shell de gerenciamento do servidor de negócios: clique em **Iniciar**, clique em **Todos os programas**, clique em **Skype para Business Server**e clique em **Skype do Shell de gerenciamento do servidor de Business**.

2.  Execute o cmdlet **New-CsHostingProvider** para criar e configurar o provedor de hospedagem. Por exemplo, execute:
    
        New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification -Enabled $True -EnabledSharedAddressSpace $False -HostsOCSUsers $False -IsLocal $False
    
    O exemplo anterior define os seguintes parâmetros:
    
      - **Identidade** Especifica um identificador de valor de cadeia de caracteres exclusiva para o provedor de hospedagem que você está criando. Observe que o comando falhará se um provedor existente já tiver sido configurado com essa identidade.
    
      - **ProxyFQDN** especifica o nome de domínio totalmente qualificado (FQDN) para o servidor de proxy usado pelo provedor de hospedagem. Esse valor não pode ser modificado. Se o provedor de hospedagem alterar o seu servidor proxy, será necessário excluir e recriar a entrada desse provedor.
    
      - **VerificationLevel** Especifica como (ou se) as mensagens enviadas de um provedor de hospedagem são verificadas para garantir que sejam enviados a partir daquele provedor.
    
      - **Habilitado ** indica se a conexão de rede entre seu domínio e o provedor de hospedagem está habilitado. As mensagens não podem ser trocadas entre as duas organizações até que esse valor seja definido como **Verdadeiro **.
    
      - **EnabledSharedAddressSpace ** indica se o provedor de hospedagem está sendo usado em um cenário de espaço de endereço SIP compartilhado (domínio dividido).
    
      - **HostsOCSUsers** indica se o provedor de hospedagem é usado para hospedar o Skype para contas de servidores de negócios. Se estiver definido como **Falso **, o provedor hospedará outros tipos de conta, como contas do Microsoft Exchange.
    
      - **IsLocal** indica se o servidor proxy usado pelo provedor de hospedagem está contido dentro de sua Skype para a topologia de servidor de negócios.
    
    Para obter detalhes sobre como usar esse cmdlet, consulte [New-CsHostingProvider](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsHostingProvider).

## <a name="configure-user-access-for-federation-with-a-skype-for-business-online-customer"></a>Configurar o acesso de usuário para federação com um Skype para cliente Business Online 

Você deve configurar o usuário contas de todos os usuários em sua organização para que eles possam ser pode se comunicar com parceiros federados. Essa configuração é aplicada para todos os parceiros federados, incluindo qualquer Skype Microsoft para domínios Business Online do cliente com o qual você oferecer suporte à Federação. Para obter detalhes sobre como configurar o suporte de federação para contas de usuário, consulte [Configurar políticas para controlar federados acesso de usuário](../external-access-policies/configure-policies-to-control-federated-user-access.md) e [atribuir uma política de acesso de usuário externo para uma Skype para negócios de usuário habilitado](../external-access-policies/assign-an-external-user-access-policy.md).

## <a name="verify-communications-with-a-skype-for-business-online-customer-in-skype-for-business-server"></a>Verificar as comunicações com um Skype para cliente Business Online no Skype para Business Server

Para habilitar o Skype para usuários de negócios em sua organização para se comunicar com usuários de um Skype para cliente Business Online, você deve ter concluído as etapas a seguir:

  - Atendidos todos os pré-requisitos. Isso inclui a implantação interna e suportam de servidores de borda, permitindo a federação para sua organização e configurando as contas de usuário. Para obter detalhes, consulte [pré-requisitos para a federação com um Skype para Business Online do cliente](#prerequisites-for-federating-with-a-skype-for-business-online-customer).
  - Suporte ao acesso de domínio configurado em sua implantação interna. Isso inclui a criação de uma entrada de provedor de host e a configuração de sua implantação para permitir o acesso do Skype para domínio Business Online do cliente. Para obter detalhes, consulte [federação configurar suporte para um Skype para domínio Business Online](#configure-federation-support-for-a-skype-for-business-online-domain).
  - Configurado suas contas de usuário para oferecer suporte à Federação. Para obter detalhes, consulte [Configurar o acesso de usuário para federação com um Skype para Business Online do cliente](#configure-user-access-for-federation-with-a-skype-for-business-online-customer).

Depois de concluir todas estas etapas e o administrador do Skype para o cliente Business Online conclui todas a configuração dos seus serviços online para oferecer suporte à Federação com sua organização, verificar as comunicações Testando as comunicações entre um usuário interno em sua organização e usuários do Skype para cliente Business Online. Se a comunicação não for bem-sucedida, use a ferramenta de log do seu servidor de borda para capturar arquivos de log e rastreamento para solucionar o problema. 
