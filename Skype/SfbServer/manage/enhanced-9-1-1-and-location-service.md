---
title: Gerenciar 9-1-1 avançado e o serviço De localização
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Skype for Business Server suporte a chamadas Aprimoradas 9-1-1 (E9-1-1) de Skype for Business clientes. Quando você configura o Skype for Business Server para E9-1-1, as chamadas de emergência feitas do Skype for Business incluem informações de ERL (Local de Resposta de Emergência) do banco de dados do Serviço de Informações de Localização.
ms.openlocfilehash: 5b002e4043cb400b5f22a4b11bc70941a88abc2a
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676003"
---
# <a name="manage-enhanced-9-1-1-and-the-location-service-in-skype-for-busines-server"></a>Gerenciar 9-1-1 avançado e o serviço De localização no Skype para o Busines Server

Skype for Business Server suporte a chamadas Aprimoradas 9-1-1 (E9-1-1) de Skype for Business clientes. Quando você configura o Skype for Business Server para E9-1-1, as chamadas de emergência feitas do Skype for Business incluem informações de ERL (Local de Resposta de Emergência) do banco de dados do Serviço de Informações de Localização. Use os procedimentos neste artigo para gerenciar a política de localização.

> [!Note]
> Para obter detalhes sobre como implantar recursos Enterprise Voice avançados, como E9-1-1 e o serviço informações de localização, consulte Implantar recursos Enterprise Voice [avançados](../deploy/deploy-enterprise-voice/deploy-advanced-enterprise-voice-features.md).

No Skype for Business Server, você pode usar a política de localização para aplicar configurações relacionadas à funcionalidade Aprimorada 9-1-1 (E9-1-1) e às configurações de local para usuários ou contatos. A política de local determina se o usuário está habilitado para o E9-1-1 e, se estiver, qual vai ser o comportamento de uma chamada de emergência. Por exemplo, é possível usar a política de local para definir o número que constitui uma chamada de emergência (911 nos Estados Unidos), se a segurança da empresa deve ser automaticamente notificada e como a chamada é roteada.

Você pode configurar políticas de localização do grupo **configuração de** rede no Skype for Business Server Painel de Controle. No Skype for Business Server Painel de Controle você pode exibir, criar, modificar ou excluir políticas de localização. Use o procedimento a seguir para exibir informações sobre políticas de localização. 


## <a name="view-location-policy-information"></a>Exibir informações da política de localização 

1.  De uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou é atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL Administração para abrir o Skype for Business Server Painel de Controle. 

3.  Na barra de navegação à esquerda, clique em **Configuração de** Rede e, em seguida, clique em **Política de Local**.

4.  Na página **Política de local**, selecione a política de local que você quer modificar.

5.  No menu **Editar**, clique em **Mostrar detalhes**.
 
    > [!NOTE]  
    > Você pode visulizar informações apenas de uma política de local por vez.

Uma política única, chamada de Global, existe por padrão e não pode ser excluída ou renomeada. Porém, você pode modificar a política Global. Essa política será aplicada a todos os usuários e contatos, a não ser que você crie políticas de sites ou políticas por usuário. As políticas por usuário devem ser aplicadas a usuários específicos.


## <a name="create-or-modify-a-location-policy"></a>Criar ou modificar uma política de localização 

No Skype for Business Server, você pode substituir a quantidade padrão de tempo entre solicitações de cliente para uma atualização de localização do serviço informações de localização. O valor padrão é de 4 horas. Use o cmdlet **Set-CsLocationPolicy** com o parâmetro LocationRefreshInterval para substituir o valor padrão.


### <a name="to-create-a-new-location-policy-in-the-skype-for-business-server-control-panel"></a>Para criar uma nova política de localização no Skype for Business Server Painel de Controle

1.  De uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou é atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL Administração para abrir o Skype for Business Server Painel de Controle. 

3.  Na barra de navegação à esquerda, clique em **Configuração de** Rede e, em seguida, clique em **Política de Local**.

4.  Na página **Política de** Local, clique em **Novo** e selecione o tipo de política que você deseja criar:
    
      - Para criar uma política de site, clique em **Política de site**. Em **Selecionar um Site**, escolha o site ao qual você deseja que a política seja aplicada e clique em **OK**. Na página **Nova Política de** Local, o  campo Escopo contém o **valor Site** e o campo  Nome contém o nome do site escolhido. Não é possível modificar nenhum desses campos. Uma política de site é aplicada automaticamente a todos os usuários no site especificado e substitui a política global para esses usuários.
    
      - Para criar uma **política de usuário**, clique **em Política de usuário**. Na Nova **Política de Local**, o **campo Escopo** contém o valor **Usuário**. Não é possível modificar esse valor. No campo **Nome** , digite o nome que você deseja dar a essa política. Uma política de usuário não se aplica automaticamente a nenhum usuário. Depois de criar a política de usuário, você deve conceder manualmente a política aos usuários ou sites de rede aos quais deseja aplicar a política.

5.  Preencha os campos restantes da seguinte maneira:
    
      - **Habilitar serviços de emergência aprimorados**   Marque essa caixa de seleção para habilitar os usuários associados a essa política para E9-1-1. Quando os serviços de emergência estão habilitados, Skype for Business Server clientes recuperarão informações de localização sobre o registro e incluirão essas informações quando uma chamada de emergência for feita.
    
      - **Localização**   Especifique um dos seguintes valores:
        
          - **Necessário**   O usuário será solicitado a inserir informações de local quando o cliente se registrar em um novo local. O usuário pode recusar o aviso, sem digitar qualquer informação. Se as informações são inseridas, uma chamada de emergência primeiro será atendida pelo provedor de serviços de emergência para verificar o local antes de ser roteada para o operador PSAP (Ponto de Atendimento de Segurança Pública) (ou seja, o operador 911).
        
          - **Não obrigatório**   O usuário não será solicitado a fornecer um local. Quando uma chamada é feita sem informações de localização, o provedor de serviços de emergência atenderá à chamada e solicitará um local.
        
          - **Disclaimer**   Essa opção é a mesma que **Obrigatório,** exceto que o usuário não pode ignorar o prompt sem inserir informações de localização. O usuário ainda pode concluir uma chamada de emergência, mas nenhuma outra chamada pode ser concluída sem inserir as informações. Além disso, o texto de isenção de responsabilidade será exibido para o usuário que pode alertá-lo sobre as consequências do declínio para inserir informações de localização. Para definir o texto de isenção de responsabilidade, você deve usar o Shell de Gerenciamento do Skype for Business Server para executar o cmdlet **Set-CsLocationPolicy** ou o cmdlet **New-CsLocationPolicy** com o parâmetro EnhancedEmergencyServiceDisclaimer. Para obter detalhes, [consulte Set-CsLocationPolicy](/powershell/module/skype/Set-CsLocationPolicy) [ou New-CsLocationPolicy](/powershell/module/skype/New-CsLocationPolicy).
          
    
      - **Use o local para serviços** de emergência Skype for Business pode usar informações de localização por vários motivos (por exemplo, para notificar os colegas de equipe da sua localização atual). Marque essa caixa de seleção para garantir que as informações de localização só estão disponíveis para uso com uma chamada de emergência.
    
      - **Uso de PSTN**   O uso de PSTN (rede telefônica pública comuada) que será usado para determinar qual rota de voz será usada para rotear chamadas de emergência de clientes que usam esse perfil. A rota associada a esse uso deve apontar para um tronco SIP dedicado a chamadas de emergência ou a um gateway de Emergency Location Identification Number (ELIN) que encaminha as chamadas de emergência ao Public Safety Answering Point (PSAP) mais próximo.
    
      - **Número de discagem de emergência**   O número discado para acessar os serviços de emergência. Nos Estados Unidos, esse valor é 911. A cadeia de caracteres deve ser composta pelos dígitos 0 a 9 e pode ter entre um e dez dígitos de comprimento.
    
      - **Máscara de discagem de emergência**   Um número que você deseja converter no valor do valor do número de discagem de emergência quando ele é discado. Por exemplo, se você inserir um valor de 212 nesse campo e o campo número de discagem de emergência tiver um valor de 911, se um usuário discar 212, a chamada será feita para 911. Isso permite a discagem de números de emergência alternativos e ainda assim acessar os serviços de emergência (por exemplo, se alguém de um país ou região com um número de emergência diferente tenta discar o número desse país ou região em vez do número para o país ou região atual). É possível definir múltiplas máscaras de discagem de emergência separando os valores com ponto e vírgulas. Por exemplo, 212;414. O comprimento máximo da cadeia de caracteres é 100. Cada caractere deve ser um dígito entre 0 e 9.
      

        > [!IMPORTANT]  
        > Garanta que o valor da máscara de discagem especificado não seja igual a um número no intervalo da órbita de estacionamento de chamadas. O roteamento do estacionamento de chamadas terá precedência sobre a conversão de cadeias de caracteres de discagem de emergência. Para ver os intervalos de órbita do estacionamento de chamada existentes, clique em Recursos de Voz na barra de navegação à esquerda e clique em **Estacionamento de Chamada**. 

    
      - **URI de notificação**   Um ou mais URIs (Uniform Resource Identifiers) SIP serão notificados quando uma chamada de emergência for feita. Por exemplo, o escritório de segurança da empresa poderia ser avisado, por meio de uma mensagem instantânea, sempre que ocorrer uma chamada de emergência. Se a localização do chamador estiver disponível, ela será incluída na notificação. Vários URIs do SIP podem ser incluídos como uma lista separada por vírgulas. Por exemplo, "sip:security@litwareinc.com","sip:kmyer@litwareinc.com". Há suporte para listas de distribuição. A string precisa ter de 1 a 256 caracteres e precisa começar com o prefixo "sip:". Antes de clicar no campo URI de Notificação, um exemplo é exibido.
    
      - **URI de conferência**   O URI SIP, nesse caso, o número de telefone de terceiros que será conferênciado em todas as chamadas de emergência que forem feitas. Por exemplo, o escritório de segurança da empresa pode receber uma chamada quando uma chamada de emergência é feita e escutar ou participar dessa chamada (dependendo do valor fornecido no campo **modo conferência).** A cadeia de caracteres deve ter entre um e 256 caracteres de comprimento e deve começar com o prefixo sip:. Um exemplo é exibido até você clicar dentro desse campo.
    
      - **Modo de conferência**   Se você especificar um valor no campo **URI** de Conferência, o modo  conferência determinará se um terceiro pode participar da chamada ou só pode escutar. Especifique uma das seguintes opções:
        
          - **Unidirecional**   Um terceiro só pode escutar a conversa entre o chamador e o operador PSAP.
        
          - **Bidirecional**   Um terceiro pode escutar e participar da chamada entre o chamador e o operador PSAP.

6.  Clique em **Confirmar**.


    > [!IMPORTANT]  
    > Quando você cria uma política de usuário, inicialmente essa política não se aplica a nenhum usuário ou sites de rede. Para aplicar a política a um usuário, clique **em Usuários** na barra de navegação à esquerda. Localize o usuário ao qual você deseja aplicar a política. No painel **Ações**, clique em **Mostrar detalhes**. Na página **Editar Usuário do Servidor**, selecione a nova política de local na  lista suspensa política de local e clique em **Confirmar**.<BR>Para aplicar a política a um site de rede, clique em **Configuração** de Rede na barra de navegação à esquerda e clique em **Site**. Localize o site de rede ao qual você deseja aplicar a política. No painel **Ações**, clique em **Mostrar detalhes**. Em **Editar Site**, selecione a nova política de local na lista **suspensa** política de local e clique em **Confirmar**.


### <a name="to-modify-a-location-policy-in-the-skype-for-business-server-control-panel"></a>Para modificar uma política de localização no Skype for Business Server Painel de Controle

1.  De uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou é atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL Administração para abrir o Skype for Business Server Painel de Controle. 

3.  Na barra de navegação à esquerda, clique em **Configuração de** Rede e, em seguida, clique em **Política de Local**.

4.  Na página **Política de local**, selecione a política de local que você quer modificar.

5.  No menu **Editar**, clique em **Mostrar detalhes**.

6.  Na página **Editar Política de** Local, modifique os campos conforme necessário (para obter detalhes, consulte a Etapa 5 nos procedimentos "Para criar uma nova política de local" anteriormente neste tópico).

7.  Clique em **Confirmar**.

        
## <a name="delete-a-location-policy"></a>Excluir uma política de localização


1.  De uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou é atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL Administração para abrir o Skype for Business Server Painel de Controle. 

3.  Na barra de navegação à esquerda, clique em **Configuração de** Rede e, em seguida, clique em **Política de Local**.

4.  Na página **Política de local**, selecione a política de local que você quer excluir.
   
    > [!NOTE]  
    > Você pode excluir mais que uma política de local ao mesmo tempo. Para isso, mantenha a tecla CTRL e selecione várias políticas. Ou, para selecionar todas as políticas, clique em **Selecionar tudo** no menu **Editar**.


5.  No menu **Editar**, clique em **Excluir**.

6.  Clique em **OK**.

    > [!IMPORTANT]  
    > Você não pode excluir uma política de local Global. Se você tentar excluir a política Global, você receberá uma mensagem de aviso, e essa política será redefinida aos seus valores padrão.


## <a name="see-also"></a>Confira também

[Criar ou modificar sites de rede](network-management/call-admission-control/managing-call-admission-control-for-sites.md#create-or-modify-network-sites)

[New-CsLocationPolicy](/powershell/module/skype/New-CsLocationPolicy)  

[Set-CsLocationPolicy](/powershell/module/skype/Set-CsLocationPolicy) 
 
[Remove-CsLocationPolicy](/powershell/module/skype/Remove-CsLocationPolicy)  

[Get-CsLocationPolicy](/powershell/module/skype/Get-CsLocationPolicy)