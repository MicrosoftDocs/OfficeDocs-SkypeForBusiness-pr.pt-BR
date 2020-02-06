---
title: Gerenciar o 9-1-1 avançado e o serviço de localização
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: O Skype for Business Server é compatível com a chamada 9-1-1 (E9-1-1) reforçada dos clientes do Skype for Business. Quando você configura o Skype for Business Server para E9-1-1, as chamadas de emergência feitas pelo Skype for Business incluem informações de local de resposta de emergência (ERL) do banco de dados do serviço de informações de localização.
ms.openlocfilehash: de02c4a9a3210220e368d87d4ae8e21a80f3dbac
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818422"
---
# <a name="manage-enhanced-9-1-1-and-the-location-service-in-skype-for-busines-server"></a>Gerenciar o 9-1-1 aprimorado e o serviço de localização no Skype para visita Server

O Skype for Business Server é compatível com a chamada 9-1-1 (E9-1-1) reforçada dos clientes do Skype for Business. Quando você configura o Skype for Business Server para E9-1-1, as chamadas de emergência feitas pelo Skype for Business incluem informações de local de resposta de emergência (ERL) do banco de dados do serviço de informações de localização. Use os procedimentos deste artigo para gerenciar a política de localização.

> [!Note]
> Para obter detalhes sobre a implantação de recursos avançados do Enterprise Voice, como E9-1-1 e o local Information Service, consulte [implantar recursos avançados do Enterprise Voice](../deploy/deploy-enterprise-voice/deploy-advanced-enterprise-voice-features.md).

No Skype for Business Server, você pode usar a política de localização para aplicar configurações relacionadas à funcionalidade Enhanced 9-1-1 (E9-1-1) e às configurações de localização para usuários ou contatos. A política de localização determina se um usuário está habilitado para E9-1-1 e, em caso afirmativo, qual é o comportamento de uma chamada de emergência. Por exemplo, você pode usar a política de localização para definir qual número constitui uma chamada de emergência (por exemplo, 911 nos Estados Unidos), se a segurança corporativa deve ser notificada automaticamente e como a chamada deve ser roteada.

Você pode configurar as políticas de localização no grupo de **configuração de rede** no painel de controle do Skype for Business Server. No painel de controle do Skype for Business Server, você pode exibir, criar, modificar ou excluir políticas de localização. Use o procedimento a seguir para exibir informações sobre as políticas de localização. 


## <a name="view-location-policy-information"></a>Exibir informações de política de localização 

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server. 

3.  Na barra de navegação à esquerda, clique em **configuração de rede**e, em seguida, clique em **política de localização**.

4.  Na página **política de localização** , selecione a política de localização que você deseja modificar.

5.  No menu **Editar**, clique em **Exibir detalhes**.
 
    > [!NOTE]  
    > Você só pode exibir informações sobre uma política de localização de cada vez.

Uma única política, chamada global, existe por padrão e não pode ser excluída ou renomeada. No entanto, você pode modificar a política global. Esta política será aplicada a todos os usuários e contatos, a menos que você crie políticas de site ou políticas por usuário. Políticas por usuário devem ser aplicadas a usuários específicos.


## <a name="create-or-modify-a-location-policy"></a>Criar ou modificar uma política de localização 

No Skype for Business Server, você pode substituir a quantidade de tempo padrão entre solicitações do cliente para uma atualização de localização do serviço de informações de localização. O valor padrão é de 4 horas. Use o cmdlet **set-CsLocationPolicy** com o parâmetro LocationRefreshInterval para substituir o valor padrão.


### <a name="to-create-a-new-location-policy-in-the-skype-for-business-server-control-panel"></a>Para criar uma nova política de localização no painel de controle do Skype for Business Server

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server. 

3.  Na barra de navegação à esquerda, clique em **configuração de rede**e, em seguida, clique em **política de localização**.

4.  Na página **política de local** , clique em **novo** e selecione o tipo de política que você deseja criar:
    
      - Para criar uma política de site, clique em **política do site**. Em **selecionar um site**, escolha o site ao qual você deseja aplicar a política e clique em **OK**. Na página **nova política de localização** , o **campo escopo** contém o valor **site**e o campo **nome** contém o nome do site que você escolheu. Não é possível modificar nenhum desses campos. Uma política de site é automaticamente aplicada a todos os usuários do site especificado e substitui a política global para esses usuários.
    
      - Para criar uma **política de usuário**, clique em **política de usuário**. Na **nova política de localização**, o campo **escopo** contém o valor **usuário**. Não é possível modificar esse valor. No campo **nome** , digite o nome que você deseja dar a essa política. Uma política de usuário não se aplica automaticamente a nenhum usuário. Depois de criar a política de usuário, você deve conceder manualmente a política aos usuários ou sites de rede aos quais deseja aplicar a política.

5.  Preencha os campos restantes da seguinte maneira:
    
      - **Habilitar serviços**   de emergência aprimorados Marque esta caixa de seleção para habilitar os usuários associados a essa política para E9-1-1. Quando os serviços de emergência estiverem habilitados, os clientes do Skype for Business Server recuperarão as informações de localização no registro e incluirão essas informações quando forem feitas uma chamada de emergência.
    
      - **Location**   especifique um dos seguintes valores:
        
          - **Obrigatório**   o usuário será solicitado a inserir informações de localização quando o cliente se registrar em um novo local. O usuário pode ignorar a solicitação sem inserir informações. Se as informações forem inseridas, uma chamada de emergência será atendida primeiramente pelo provedor de serviços de emergência para verificar o local antes de ser roteado para o operador de ponto de resposta de segurança pública (PSAP) (ou seja, o operador 911).
        
          - **Não obrigatório**   o usuário não será solicitado a fornecer um local. Quando uma chamada é feita sem informações de localização, o provedor de serviços de emergência atende a chamada e solicita um local.
        
          - **Isenção de responsabilidade**   essa opção é a mesma que a **necessária** , exceto que o usuário não pode ignorar o prompt sem inserir informações de localização. O usuário ainda pode concluir uma chamada de emergência, mas nenhuma outra chamada pode ser completada sem inserir as informações. Além disso, o texto de isenção de responsabilidade será exibido para o usuário que pode alertá-lo sobre as conseqüências de se recusar a inserir informações de localização. Para definir o texto de isenção de responsabilidade, você deve usar o Shell de gerenciamento do Skype for Business Server para executar o cmdlet **set-CsLocationPolicy** ou o cmdlet **New-CsLocationPolicy** com o parâmetro EnhancedEmergencyServiceDisclaimer. Para obter detalhes, consulte [set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsLocationPolicy) ou [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsLocationPolicy).
          
    
      - **Usar local somente para serviços de emergência** O Skype for Business pode usar as informações de localização por vários motivos (por exemplo, para notificar os colegas de trabalho sobre sua localização atual). Marque esta caixa de seleção para garantir que as informações de localização estejam disponíveis somente para uso com uma chamada de emergência.
    
      - **Uso da PSTN**   o uso de rede telefônica pública comutada (PSTN) que será usado para determinar qual rota de voz será usada para direcionar as chamadas de emergência dos clientes que usam esse perfil. A rota associada a esse uso deve apontar para um tronco SIP dedicado a chamadas de emergência ou a um gateway de Emergency Location Identification Number (ELIN) que encaminha as chamadas de emergência ao Public Safety Answering Point (PSAP) mais próximo.
    
      - **Número de discagem de emergência**   o número discado para acessar serviços de emergência. Nos Estados Unidos, esse valor é 911. A cadeia de caracteres deve ser feita dos dígitos de 0 a 9 e pode ter de 1 a 10 dígitos.
    
      - **Máscara de discagem de emergência**   um número que você deseja traduzir para o valor do valor do número de discagem de emergência quando ele for discado. Por exemplo, se você inserir um valor de 212 nesse campo e o campo de número de discagem de emergência tiver um valor de 911, se um usuário discar 212, a chamada será feita a 911. Isso permite a discagem de números de emergência alternativos e ainda assim acessar os serviços de emergência (por exemplo, se alguém de um país ou região com um número de emergência diferente tenta discar o número desse país ou região em vez do número para o país ou região atual). É possível definir várias máscaras de discagem de emergência separando os valores com ponto e vírgulas. Por exemplo, 212;414. O comprimento máximo da cadeia é de 100 caracteres. Cada caractere precisa ser um dígito de 0 a 9.
      

        > [!IMPORTANT]  
        > Certifique-se de que o valor de máscara de discagem especificado não seja igual a um número em um intervalo de linha de estacionamento de chamada. O roteamento do parque de chamadas terá precedência com a conversão de cadeia de discagem de emergência. Para ver os intervalos de o parque de chamadas existentes, clique em **recursos de voz** na barra de navegação à esquerda e clique em **ligar para estacionamento**. 

    
      - **URI de notificação**   um ou mais URIs (Uniform Resource Identifiers) SIP a serem notificados quando uma chamada de emergência é feita. Por exemplo, o escritório de segurança da empresa pode ser notificado por uma mensagem instantânea sempre que uma chamada de emergência é feita. Se a localização do chamador estiver disponível, essa localização será incluída na notificação. Vários URIs SIP podem ser incluídos como uma lista separada por vírgulas. Por exemplo, "sip:security@litwareinc.com","sip:kmyer@litwareinc.com". As listas de distribuição são aceitas. A cadeia de cadeia de caracteres precisa ter de 1 a 256 caracteres e precisa começar com o prefixo "sip:". Antes de clicar no campo URI da notificação, um exemplo é exibido.
    
      - **URI da conferência**   o URI SIP, nesse caso, o número de telefone de terceiros que serão em conferência para qualquer chamada de emergência feita. Por exemplo, o Office de segurança da empresa pode receber uma chamada quando uma chamada de emergência é feita e ouvir ou participar dessa chamada (dependendo do valor fornecido no campo **modo de conferência** ). A cadeia de caracteres precisa ter de 1 a 256 caracteres e precisa começar com o prefixo sip:. Um exemplo é exibido até que você clique dentro desse campo.
    
      - **Modo**   de conferência se você especificar um valor no campo **URI de conferência** , o modo de **conferência** determinará se uma terceira parte pode participar da chamada ou somente pode ouvi-la. Especifique uma das seguintes opções:
        
          - **Unidirecional**   um terceiro só pode ouvir a conversa entre o chamador e o operador de PSAP.
        
          - **Bidirecional**   um terceiro pode ouvir e participar da chamada entre o chamador e o operador PSAP.

6.  Clique em **Confirmar**.


    > [!IMPORTANT]  
    > Quando você cria uma política de usuário, inicialmente essa política não se aplica a nenhum usuário ou site de rede. Para aplicar a política a um usuário, clique em **usuários** na barra de navegação à esquerda. Localize o usuário ao qual você deseja aplicar a política. No menu **Editar**, clique em **Exibir detalhes**. Na página **Editar usuário do servidor** , selecione a lista de novos locais na lista suspensa **política de localização** e clique em **confirmar**.<BR>Para aplicar a política a um site de rede, clique em **configuração de rede** na barra de navegação à esquerda e, em seguida, clique em **site**. Localize o site de rede ao qual você deseja aplicar a política. No menu **Editar**, clique em **Exibir detalhes**. Em **Editar site**, selecione a nova política de localização na lista suspensa **diretiva de local** e clique em **confirmar**.


### <a name="to-modify-a-location-policy-in-the-skype-for-business-server-control-panel"></a>Para modificar uma política de localização no painel de controle do Skype for Business Server

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server. 

3.  Na barra de navegação à esquerda, clique em **configuração de rede**e, em seguida, clique em **política de localização**.

4.  Na página **política de localização** , selecione a política de localização que você deseja modificar.

5.  No menu **Editar**, clique em **Exibir detalhes**.

6.  Na página **Editar política de local** , modifique os campos conforme necessário (para obter detalhes, veja a etapa 5 nos procedimentos "para criar uma nova política de local" anteriormente neste tópico).

7.  Clique em **Confirmar**.

        
## <a name="delete-a-location-policy"></a>Excluir uma política de localização


1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server. 

3.  Na barra de navegação à esquerda, clique em **configuração de rede**e, em seguida, clique em **política de localização**.

4.  Na página **política de localização** , selecione a política de localização que você deseja excluir.
   
    > [!NOTE]  
    > Você pode excluir mais de uma política de localização de cada vez. Para fazer isso, pressione CTRL e selecione várias políticas enquanto mantém a tecla CTRL pressionada. Ou, para selecionar todas as políticas, clique em **selecionar tudo** no menu **Editar** .


5.  No menu **Editar** , clique em **excluir**.

6.  Clique em **OK**.

    > [!IMPORTANT]  
    > Não é possível excluir a política de localização global. Se você tentar excluir a política global, receberá uma mensagem de aviso e essa política será redefinida para seus valores padrão.


## <a name="see-also"></a>Confira também

[Criar ou modificar sites de rede](network-management/call-admission-control/managing-call-admission-control-for-sites.md#create-or-modify-network-sites)

[New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsLocationPolicy)  

[Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsLocationPolicy) 
 
[Remove-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsLocationPolicy)  

[Get-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsLocationPolicy)  
