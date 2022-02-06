---
title: Configurando o suporte de federação para um cliente do Skype for Business Online
ms.reviewer: null
'ms:assetid': e5f7f38d-ede5-4af3-88c2-026e8a78df12
'ms:mtpsurl': 'https://technet.microsoft.com/en-us/library/Hh202193(v=OCS.15)'
'ms:contentKeyID': 48185669
mtps_version: v=OCS.15
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
description: 'Se você implantar Skype for Business em sua organização, poderá federar com os domínios de um ou mais clientes Skype for Business Online. '
---

# <a name="configuring-federation-support-for-a-skype-for-business-online-customer-in-skype-for-business-server"></a>Configurando o suporte de federação para um cliente Skype for Business Online no Skype for Business Server

Você pode fornecer serviços de comunicação para usuários em sua organização de qualquer uma das seguintes maneiras:

- Implantando Skype for Business Server em sua organização (conhecidos como serviços *locais) e* configurando Skype for Business contas de usuário em sua organização.
- Configurar uma conta de cliente do Microsoft Skype for Business Online com um Provedor de Hospedagem e configurar contas de usuário com o Provedor de Hospedagem (conhecidos como *serviços online*).

Se você implantar Skype for Business em sua organização, poderá federar com os domínios de um ou mais clientes Skype for Business Online. Para habilitar a federação entre usuários de sua implantação Skype for Business local e usuários de um cliente Skype for Business Online, você deve configurar o suporte para o domínio e os usuários do cliente Skype for Business Online.

[!INCLUDE [sfbo-retirement-skype](../../../../Hub/includes/sfbo-retirement.md)]

> [!NOTE]  
> Esta documentação descreve apenas os procedimentos para configurar sua organização para dar suporte à federação com um cliente Skype for Business Online. Esta documentação não descreve os procedimentos para configurar o cliente Skype for Business Online para dar suporte à federação.

## <a name="prerequisites-for-federating-with-a-skype-for-business-online-customer"></a>Pré-requisitos para federar com um cliente Skype for Business Online

Para federar com um cliente Skype for Business Online, você já deve ter concluído a implantação inicial e a configuração do Skype for Business Server em sua organização. Isso inclui:

- Implantando pelo menos um servidor Edição Standard ou um pool de front-end Edição Enterprise em sua organização.
- Habilitando contas de usuário internas para Skype for Business Server.
- Implantando pelo menos um Servidor de Borda e os outros componentes necessários para dar suporte ao acesso de usuário externo. Para obter detalhes, consulte [Managing federation and external access to Skype for Business Server](../managing-federation-and-external-access.md).
- Habilitar suporte de federação dentro da sua organização e configurar o método adequado para controlar o acesso de domínios federados. Para obter detalhes, consulte [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md) and [Manage SIP federated providers for your organization](../sip-providers/manage-sip-federated-providers-for-your-organization.md).
- Habilitar acesso de usuário externo para usuários na sua organização. Para obter detalhes, [consulte Assign an external user access policy to a Skype for Business enabled user](../external-access-policies/assign-an-external-user-access-policy.md).

## <a name="configure-federation-support-for-a-skype-for-business-online-domain"></a>Configurar o suporte de federação para um domínio Skype for Business Online

A federação com um cliente Skype for Business Online exige que você conclua as seguintes etapas:

- Configure o suporte para o domínio do cliente Skype for Business Online 2010 (por exemplo, contoso.onmicrosoft.com). Conforme especificado em [Pré-requisitos para federar](#prerequisites-for-federating-with-a-skype-for-business-online-customer) com um cliente Skype for Business Online, você já deve ter habilitado a federação para sua organização. A habilitação da federação exige a especificação do método a ser usado para controlar o acesso dos domínios federados. Caso tenha configurado sua organização para usar a descoberta, a inclusão do domínio na sua lista de organizações permitidas é opcional. Se você não habilitar a descoberta de domínio, deverá adicionar o nome de domínio do cliente Skype for Business Online à lista de domínios permitidos. Você pode adicionar um nome de domínio usando Skype for Business Server Painel de Controle ou executando o cmdlet **New-CSAllowedDomain**. Para obter detalhes sobre como usar Skype for Business Server Painel de Controle, incluindo a habilitação da descoberta de domínios, consulte [Manage SIP federated providers for your organization in Skype for Business Server](../sip-providers/manage-sip-federated-providers-for-your-organization.md). Para obter detalhes sobre como usar o cmdlet **New-CSAllowedDomain** para adicionar um domínio, consulte [New-CsAllowedDomain](/powershell/module/skype/New-CsAllowedDomain).

  > [!NOTE]  
  > Um Skype for Business online pode ter vários domínios. Se você deseja federar com mais de um dos domínios, configure o suporte para cada domínio individual com o qual deseja dar suporte à federação, e o administrador do cliente do Skype for Business Online deve habilitar a federação para que cada um dos domínios seja federado.

- Configure o suporte para o provedor de hospedagem do domínio do cliente Skype for Business Online com o qual você deseja federar. Use os procedimentos desta seção para configurar o suporte ao provedor de hospedagem.

  > [!NOTE]  
  > Esta etapa é necessária apenas para federação com um domínio de um cliente Skype for Business Online, não para federação com qualquer domínio implantado no local no local de um parceiro federado.

### <a name="to-configure-support-for-a-hosting-provider"></a>Configurar o suporte para um provedor de hospedagem

1. Em um Servidor front-end, inicie o shell de gerenciamento Skype for Business Server: clique em **Iniciar, clique** em Todos os **Programas, Skype for Business Server** clique em Skype for Business Server **Shell de Gerenciamento**.

2. Execute o cmdlet **New-CsHostingProvider** para criar e configurar um provedor de hospedagem. Por exemplo, execute:

    ```powershell
    New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification -Enabled $True -EnabledSharedAddressSpace $False -HostsOCSUsers $False -IsLocal $False
    ```

    O exemplo anterior define os seguintes parâmetros:

    - **Identidade** especifica um identificador de valor exclusivo de cadeia de caracteres para o provedor de hospedagem que você está criando. Observe que o comando não funcionará casa haja um provedor existente já configurado com aquela Identity.

    - **ProxyFQDN** especifica o FQDN (nome de domínio totalmente qualificado) para o servidor proxy usado pelo provedor de hospedagem. Este valor não pode ser modificado. Se o provedor de hospedagem alterar seu servidor proxy, será necessário que você exclua e recrie a entrada para aquele provedor.

    - **VerificationLevel** especifica como (ou se) as mensagens enviadas de um provedor de hospedagem são verificados para garantir que sejam enviados a partir daquele provedor.

    - **Enabled** indica se a conexão de rede entre o seu domínio e o provedor de hospedagem está ativada. As mensagens não podem ser trocadas entre as duas organizações até que este valor seja definido como **True**.

    - **EnabledSharedAddressSpace** indica se o provedor de hospedagem está sendo usado em um cenário de espaço de endereço SIP compartilhado (domínio dividido).

    - **HostsOCSUsers** indica se o provedor de hospedagem é usado para hospedar Skype for Business Server contas. Se estiver definido como **Falso**, o provedor hospedará outros tipos de conta, como contas do Microsoft Exchange.

    - **IsLocal** indica se o servidor proxy usado pelo provedor de hospedagem está contido em sua topologia Skype for Business Server local.

    Para obter detalhes sobre como usar esse cmdlet, consulte [New-CsHostingProvider](/powershell/module/skype/New-CsHostingProvider).

## <a name="configure-user-access-for-federation-with-a-skype-for-business-online-customer"></a>Configurar o acesso do usuário para federação com um cliente Skype for Business Online

Você deve configurar as contas de usuário de todos os usuários em sua organização para que eles possam se comunicar com parceiros federados. Essa configuração é aplicada a todos os parceiros federados, incluindo qualquer domínio de cliente do Microsoft Skype for Business Online com os quais você suporta a federação. Para obter detalhes sobre como configurar o suporte de federação para contas de usuário, consulte [Configure policies to control federated user access](../external-access-policies/configure-policies-to-control-federated-user-access.md) and [Assign an external user access policy to a Skype for Business enabled user](../external-access-policies/assign-an-external-user-access-policy.md).

## <a name="verify-communications-with-a-skype-for-business-online-customer-in-skype-for-business-server"></a>Verificar comunicações com um cliente Skype for Business Online no Skype for Business Server

Para permitir que Skype for Business usuários em sua organização se comuniquem com usuários de um cliente Skype for Business Online, você deve ter concluído as seguintes etapas:

- Atender a todos os pré-requisitos. Isso incluir a implantação de seus servidores internos e de borda, habilitação do suporte á federação para sua organização e configuração das contas de usuário. Para obter detalhes, consulte [Pré-requisitos para federar com um cliente Skype for Business Online](#prerequisites-for-federating-with-a-skype-for-business-online-customer).
- Configurar o suporte ao acesso de domínio em sua implantação interna. Isso inclui a criação de uma entrada de provedor de host e a configuração de sua implantação para permitir o acesso Skype for Business domínio do cliente online. Para obter detalhes, consulte [Configure federation support for a Skype for Business Online domain](#configure-federation-support-for-a-skype-for-business-online-domain).
- Configurar suas contas de usuário para suportar a federação. Para obter detalhes, [consulte Configure user access for federation with a Skype for Business Online customer](#configure-user-access-for-federation-with-a-skype-for-business-online-customer).

Depois de concluir todas essas etapas e o administrador do cliente do Skype for Business Online concluir toda a configuração de seus serviços online para dar suporte à federação com sua organização, verifique as comunicações testando comunicações entre um usuário interno em sua organização e um usuário do cliente Skype for Business Online. Se a comunicação não for bem-sucedida, use a Ferramenta de Log do Servidor de Borda para capturar arquivos de log e rastreamento para solucionar o problema.
