---
title: Gerenciar o 9-1-1 avançado e serviço de localidade
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype para Business Server suporta Enhanced 9-1-1 (E9-1-1) chamando do Skype para clientes corporativos. Quando você configura Skype para Business Server para E9-1-1, as chamadas de emergência colocadas do Skype para negócios incluem informações de local de resposta de emergência (ERL) do banco de dados de serviço de informações de local.
ms.openlocfilehash: 31e1d529c8fb60145bc1ab4a22a75660d9f3ef63
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30895150"
---
# <a name="manage-enhanced-9-1-1-and-the-location-service-in-skype-for-busines-server"></a>Gerenciar 9-1-1 avançado e o serviço de local no Skype visita do servidor

Skype para Business Server suporta Enhanced 9-1-1 (E9-1-1) chamando do Skype para clientes corporativos. Quando você configura Skype para Business Server para E9-1-1, as chamadas de emergência colocadas do Skype para negócios incluem informações de local de resposta de emergência (ERL) do banco de dados de serviço de informações de local. Use os procedimentos neste artigo para gerenciar a diretiva de local.

> [!Note]
> Para obter detalhes sobre como implantar os recursos avançados do Enterprise Voice, como E9-1-1 e o serviço de informações de local, consulte [Deploy Enterprise Voice recursos avançados](../deploy/deploy-enterprise-voice/deploy-advanced-enterprise-voice-features.md).

No Skype para Business Server, você pode usar a diretiva de local para aplicar configurações que se relacionam à funcionalidade do Enhanced 9-1-1 (E9-1-1) e configurações de local para usuários ou contatos. A política de local determina se um usuário está habilitado para E9-1-1 e, em caso afirmativo, o que é o comportamento de uma chamada de emergência. Por exemplo, você pode usar a diretiva de local para definir qual número constitui uma chamada de emergência (911 nos Estados Unidos, por exemplo,), se segurança corporativa deve ser notificada automaticamente e como a chamada deve ser roteada.

Você pode configurar políticas de local a partir do grupo de **Configuração de rede** em que o Skype para painel de controle do Business Server. O Skype para painel de controle do Business Server, você pode exibir, criar, modificar ou excluir políticas de local. Use o procedimento a seguir para exibir informações sobre as políticas de local. 


## <a name="view-location-policy-information"></a>Exibir informações de política de local 

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios. 

3.  Na barra de navegação à esquerda, clique em **Configuração de rede**e, em seguida, clique em **Política de local**.

4.  Na página **Política de local** , selecione a política de local que você deseja modificar.

5.  No menu **Editar**, clique em **Exibir detalhes**.
 
    > [!NOTE]  
    > Você só pode exibir informações sobre uma política de local por vez.

Uma única política, chamada Global, existe por padrão e não pode ser excluída ou renomeada. No entanto, você pode modificar a política Global. Essa política se aplicará a todos os usuários e contatos, a menos que você crie políticas de site ou políticas por usuário. Políticas por usuário devem ser aplicadas a usuários específicos.


## <a name="create-or-modify-a-location-policy"></a>Criar ou modificar uma política de local 

No Skype para Business Server, você pode substituir a quantidade padrão de tempo entre as solicitações de cliente para uma atualização local do serviço de informações de local. O valor padrão é 4 horas. Use o cmdlet **Set-CsLocationPolicy** com o parâmetro LocationRefreshInterval para substituir o valor padrão.


### <a name="to-create-a-new-location-policy-in-the-skype-for-business-server-control-panel"></a>Para criar uma nova política de local do Skype do painel de controle do servidor de negócios

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios. 

3.  Na barra de navegação à esquerda, clique em **Configuração de rede**e, em seguida, clique em **Política de local**.

4.  Na página **Política de local** , clique em **novo** e selecione o tipo de política que você deseja criar:
    
      - Para criar uma política de site, clique em **política de Site**. Em **Selecionar um Site**, escolha o site ao qual você deseja que a diretiva aplicada e clique em **Okey**. Na página **Nova política de local** , o campo de **escopo** contém o **Site**de valor e o campo **nome** contém o nome do site escolhido. Você não pode modificar qualquer um desses campos. Uma política de site será automaticamente aplicada a todos os usuários no site especificado e substitui a política global para os usuários.
    
      - Para criar uma **política de usuário**, clique em **política de usuário**. Na **Nova política de local**, o campo de **escopo** contém o valor do **usuário**. Você não pode modificar esse valor. No campo **nome** , digite o nome que você deseja conceder a essa política. Uma política de usuário não aplicar automaticamente a todos os usuários. Depois de criar a política de usuário, você deve conceder manualmente a política aos usuários ou sites de rede para o qual você deseja política a ser aplicado.

5.  Preencha os campos restantes da seguinte maneira:
    
      - **Habilitar enhanced serviços de emergência**   marque essa caixa de seleção para permitir que os usuários associados a essa diretiva para E9-1-1. Quando os serviços de emergência estão habilitados, Skype para clientes Business Server irá recuperar informações de local no registro e incluir essa informação quando uma chamada de emergência é feita.
    
      - **Local**   especificar um dos seguintes valores:
        
          - **Necessário**   o usuário será solicitado a digitar informações de local quando o cliente se registrar em um novo local. O usuário pode recusar o aviso sem digitar qualquer informação. Se forem digitadas informações, uma chamada de emergência primeiro será atendida pelo provedor de serviços de emergência para verificar o local antes de ser roteado para o operador de PSAP atendimento público seguro ponto () (ou seja, o 911 operador).
        
          - **Não é necessário**   o usuário não será solicitado para um local. Quando uma chamada for feita sem informações de local, o provedor de serviços de emergência atenda à chamada e solicitará o local.
        
          - **Isenção de responsabilidade**   essa opção é igual a **necessários** , exceto pelo fato do usuário não pode recusar o aviso sem digitar informações de local. O usuário ainda poderá efetuar uma chamada de emergência, mas nenhuma outra chamada poderá ser efetuada sem inserindo as informações. Além disso, o texto de isenção de responsabilidade será exibido ao usuário, alertando-o sobre as consequências de se recusar a digitar informações de localização. Para definir o texto de isenção de responsabilidade, você deve usar o Skype para Business Server Management Shell para executar o cmdlet **Set-CsLocationPolicy** ou o cmdlet **New-CsLocationPolicy** com o parâmetro EnhancedEmergencyServiceDisclaimer. Para obter detalhes, consulte [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsLocationPolicy) ou [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsLocationPolicy).
          
    
      - **Usar o local para que apenas os serviços de emergência** Skype para a empresa pode usar informações de local várias finalidades (por exemplo, para notificar companheiros de sua localização atual). Marque esta caixa de seleção para garantir que as informações de local estão disponíveis apenas para uso com uma chamada de emergência.
    
      - **Uso da PSTN**   a pública comutada uso do telefone PSTN (rede) que será usado para determinar qual rota de voz será usada para rotear chamadas de emergência de clientes usando esse perfil. A rota associada a esse uso deve apontar para um tronco SIP dedicado a chamadas de emergência ou a um gateway de Emergency Location Identification Number (ELIN) que encaminha as chamadas de emergência ao Public Safety Answering Point (PSAP) mais próximo.
    
      - **Número de discagem de emergência**   o número discado para acessar os serviços de emergências. Nos Estados Unidos, esse valor é 911. A cadeia de caracteres deve ser composta pelos dígitos 0 a 9 e pode ser de 1 a 10 dígitos de comprimento.
    
      - **Máscara de discagem de emergência**   um número que você deseja converter no valor do valor de número de discagem de emergência quando ele é discado. Por exemplo, se você inserir um valor de 212 neste campo e o campo de número de discagem de emergência tem o valor 911, se um usuário discar 212 a chamada será feita para 911. Isso permite a discagem de números de emergência alternativos e ainda assim acessar os serviços de emergência (por exemplo, se alguém de um país ou região com um número de emergência diferente tenta discar o número desse país ou região em vez do número para o país ou região atual). É possível definir várias máscaras de discagem de emergência separando os valores com ponto e vírgulas. Por exemplo, 212;414. Comprimento máximo da cadeia de caracteres é 100 caracteres. Cada caractere precisa ser um dígito de 0 a 9.
      

        > [!IMPORTANT]  
        > Certifique-se de que o valor de máscara de discagem especificado não é o mesmo que um número em um intervalo de órbita de estacionamento de chamada. Roteamento de estacionamento de chamada terá precedência sobre conversão de cadeia de caracteres de discagem de emergência. Para ver os existentes intervalos de órbita de estacionamento de chamada, clique em **Recursos de voz** na barra de navegação à esquerda e clique em **Estacionamento de chamadas**. 

    
      - **URI de notificação**   um ou mais SIP URIs Uniform Resource Identifiers () para ser notificado quando for feita uma chamada de emergência. Por exemplo, o escritório de segurança da empresa poderia ser notificado por meio de uma mensagem instantânea, sempre que for feita uma chamada de emergência. Se a localização do chamador está disponível nesse local será incluído na notificação. Diversos URIs de SIP podem ser incluídos como uma lista separada por vírgulas. Por exemplo, "sip:security@litwareinc.com","sip:kmyer@litwareinc.com". Há suporte para listas de distribuição. A cadeia de cadeia de caracteres precisa ter de 1 a 256 caracteres e precisa começar com o prefixo "sip:". Antes de clicar no campo URI de notificação um exemplo é exibido.
    
      - **URI de conferência**   o URI do SIP, neste caso, o número de telefone, de terceiros que serão envolvidos em qualquer chamada de emergência que sejam feita. Por exemplo, o escritório de segurança da empresa poderia receber uma chamada quando uma chamada de emergência é feita e ouvir ou participar da chamada (dependendo do valor fornecido no campo do **modo de conferência** ). A cadeia de caracteres precisa ter de 1 a 256 caracteres e precisa começar com o prefixo sip:. Um exemplo é exibido até que você clique dentro desse campo.
    
      - **Modo de conferência**   se você especificar um valor no campo **URI de conferência** , o **modo de conferência** determina se um terceiro pode participar da chamada, ou pode apenas escutar. Especifique uma das seguintes opções:
        
          - **Unidirecional**   um terceiro só pode ouvir a conversa entre o chamador e o operador de PSAP.
        
          - **Bidirecional**   uma terceira parte poderá escutar e participar da chamada entre o chamador e o operador PSAP.

6.  Clique em **Confirmar**.


    > [!IMPORTANT]  
    > Quando você cria uma política de usuário, inicialmente essa diretiva não se aplica a qualquer usuários ou sites de rede. Para aplicar a política a um usuário, clique em **usuários** , na barra de navegação à esquerda. Encontre o usuário ao qual você deseja aplicar a política. No menu **Editar**, clique em **Exibir detalhes**. Na página **Editar usuário do servidor** , selecione a nova diretiva de local na lista suspensa **política de local** e clique em **Confirmar**.<BR>Para aplicar a política a um site de rede, clique em **Configuração de rede** na barra de navegação à esquerda e clique em **sites**. Encontre o site de rede ao qual você deseja aplicar a política. No menu **Editar**, clique em **Exibir detalhes**. Em **Editar Site**, selecione a nova diretiva de local na lista suspensa **política de local** e clique em **Confirmar**.


### <a name="to-modify-a-location-policy-in-the-skype-for-business-server-control-panel"></a>Para modificar uma política de local em que o Skype para painel de controle do servidor de negócios

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios. 

3.  Na barra de navegação à esquerda, clique em **Configuração de rede**e, em seguida, clique em **Política de local**.

4.  Na página **Política de local** , selecione a política de local que você deseja modificar.

5.  No menu **Editar**, clique em **Exibir detalhes**.

6.  Na página **Editar política de local** , modifique os campos conforme necessário (para obter detalhes, consulte a etapa 5 em "para criar uma nova política de local" procedimentos anteriormente neste tópico).

7.  Clique em **Confirmar**.

        
## <a name="delete-a-location-policy"></a>Excluir uma política de local


1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios. 

3.  Na barra de navegação à esquerda, clique em **Configuração de rede**e, em seguida, clique em **Política de local**.

4.  Na página **Política de local** , selecione a política de local que você deseja excluir.
   
    > [!NOTE]  
    > Você pode excluir mais de uma política de local por vez. Para fazer isso, pressione CTRL e selecione várias políticas, mantendo pressionada a tecla CTRL. Ou, para selecionar todas as diretivas, clique em **Selecionar tudo** no menu **Editar** .


5.  No menu **Editar** , clique em **Excluir**.

6.  Clique em **OK**.

    > [!IMPORTANT]  
    > Você não pode excluir a política de local Global. Se você tentar excluir a política Global, você receberá uma mensagem de aviso e essa diretiva será redefinida para seus valores padrão.


## <a name="see-also"></a>Consulte Também

[Criar ou modificar sites de rede](network-management/call-admission-control/managing-call-admission-control-for-sites.md#create-or-modify-network-sites)

[New-CsLocationPolicy.](https://docs.microsoft.com/powershell/module/skype/New-CsLocationPolicy)  

[Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsLocationPolicy) 
 
[Remove-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsLocationPolicy)  

[Get-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsLocationPolicy)  
