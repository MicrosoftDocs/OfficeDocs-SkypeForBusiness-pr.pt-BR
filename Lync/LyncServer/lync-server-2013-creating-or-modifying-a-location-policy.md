---
title: 'Lync Server 2013: Criando ou modificando uma política de localização'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or modifying a location policy
ms:assetid: 10338418-4da4-42df-b231-f52098c08dae
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687971(v=OCS.15)
ms:contentKeyID: 49733557
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1648e845fc3759e7083c2443013f89fb49c1b00f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740171"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-a-location-policy-in-lync-server-2013"></a>Criando ou modificando uma política de localização no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-11-01_

No Lync Server 2013, você pode usar a política de localização para aplicar configurações relacionadas à funcionalidade Enhanced 9-1-1 (E9-1-1) e às configurações de localização para usuários ou contatos. A política de localização determina se um usuário está habilitado para E9-1-1 e, em caso afirmativo, qual é o comportamento de uma chamada de emergência. Por exemplo, você pode usar a política de localização para definir qual número constitui uma chamada de emergência (por exemplo, 911 nos Estados Unidos), se a segurança corporativa deve ser notificada automaticamente e como a chamada deve ser roteada.

Você pode configurar as políticas de localização do grupo de **configuração de rede** no painel de controle do Lync Server 2013. No painel de controle do Lync Server, você pode exibir, criar, modificar ou excluir políticas de localização. Use os procedimentos desta seção para criar ou modificar uma política de localização. Para obter detalhes sobre a exclusão de políticas de localização, consulte [excluindo uma política de localização no Lync Server 2013](lync-server-2013-deleting-a-location-policy.md).

No Lync Server 2013, você pode substituir a quantidade de tempo padrão entre solicitações do cliente para uma atualização de localização do serviço de informações de localização. O valor padrão é de 4 horas. Use o cmdlet **set-CsLocationPolicy** com o parâmetro LocationRefreshInterval para substituir o valor padrão.

<div>

## <a name="to-create-a-new-location-policy-in-lync-server-control-panel"></a>Para criar uma nova política de localização no painel de controle do Lync Server

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **configuração de rede** e, em seguida, clique em **política de localização**.

4.  Na página **política de local** , clique em **novo** e selecione o tipo de política que você deseja criar:
    
      - Para criar uma política de site, clique em **política do site**. Em **selecionar um site**, escolha o site ao qual você deseja aplicar a política e clique em **OK**. Na página **nova política de localização** , o **campo escopo** contém o valor **site**e o campo **nome** contém o nome do site que você escolheu. Não é possível modificar nenhum desses campos. Uma política de site é automaticamente aplicada a todos os usuários do site especificado e substitui a política global para esses usuários.
    
      - Para criar uma **política de usuário**, clique em **política de usuário**. Na **nova política de localização**, o campo **escopo** contém o valor **usuário**. Não é possível modificar esse valor. No campo **nome** , digite o nome que você deseja dar a essa política. Uma política de usuário não se aplica automaticamente a nenhum usuário. Depois de criar a política de usuário, você deve conceder manualmente a política aos usuários ou sites de rede aos quais deseja aplicar a política.

5.  Preencha os campos restantes da seguinte maneira:
    
      - **Habilitar serviços**   de emergência aprimorados Marque esta caixa de seleção para habilitar os usuários associados a essa política para E9-1-1. Quando os serviços de emergência estiverem habilitados, os clientes do Lync Server recuperarão informações de localização no registro e incluirão essas informações quando uma chamada de emergência for feita.
    
      - **Location**   especifique um dos seguintes valores:
        
          - **Obrigatório**   o usuário será solicitado a inserir informações de localização quando o cliente se registrar em um novo local. O usuário pode ignorar a solicitação sem inserir informações. Se as informações forem inseridas, uma chamada de emergência será atendida primeiramente pelo provedor de serviços de emergência para verificar o local antes de ser roteado para o operador de ponto de resposta de segurança pública (PSAP) (ou seja, o operador 911).
        
          - **Não obrigatório**   o usuário não será solicitado a fornecer um local. Quando uma chamada é feita sem informações de localização, o provedor de serviços de emergência atende a chamada e solicita um local.
        
          - **Isenção de responsabilidade**   essa opção é a mesma que a **necessária** , exceto que o usuário não pode ignorar o prompt sem inserir informações de localização. O usuário ainda pode concluir uma chamada de emergência, mas nenhuma outra chamada pode ser completada sem inserir as informações. Além disso, o texto de isenção de responsabilidade será exibido para o usuário que pode alertá-lo sobre as conseqüências de se recusar a inserir informações de localização. Para definir o texto de isenção de responsabilidade, você deve usar o Shell de gerenciamento do Lync Server para executar o cmdlet **set-CsLocationPolicy** ou o cmdlet **New-CsLocationPolicy** com o parâmetro EnhancedEmergencyServiceDisclaimer. Para obter detalhes, consulte [set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsLocationPolicy) ou [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsLocationPolicy) na documentação do Shell de gerenciamento do Lync Server.
            
            <div>
            

            > [!NOTE]  
            > No Lync Server 2013, você pode usar a política de localização para definir diferentes isenções para locais diferentes ou conjuntos de usuários diferentes, ao contrário do Lync Server 2010, onde você pode especificar apenas um aviso global para toda a organização.

            
            </div>
    
      - **Usar local para serviços de emergência somente**   o Lync pode usar informações de localização por vários motivos (por exemplo, para notificar os colegas de sua localização atual). Marque esta caixa de seleção para garantir que as informações de localização estejam disponíveis somente para uso com uma chamada de emergência.
    
      - **Uso da PSTN**   o uso de rede telefônica pública comutada (PSTN) que será usado para determinar qual rota de voz será usada para direcionar as chamadas de emergência dos clientes que usam esse perfil. A rota associada a esse uso deve apontar para um tronco SIP dedicado a chamadas de emergência ou a um gateway de Emergency Location Identification Number (ELIN) que encaminha as chamadas de emergência ao Public Safety Answering Point (PSAP) mais próximo.
    
      - **Número de discagem de emergência**   o número discado para acessar serviços de emergência. Nos Estados Unidos, esse valor é 911. A cadeia de caracteres deve ser feita dos dígitos de 0 a 9 e pode ter de 1 a 10 dígitos.
    
      - **Máscara de discagem de emergência**   um número que você deseja traduzir para o valor do valor do número de discagem de emergência quando ele for discado. Por exemplo, se você inserir um valor de 212 nesse campo e o campo de número de discagem de emergência tiver um valor de 911, se um usuário discar 212, a chamada será feita a 911. Isso permite a discagem de números de emergência alternativos e ainda assim acessar os serviços de emergência (por exemplo, se alguém de um país ou região com um número de emergência diferente tenta discar o número desse país ou região em vez do número para o país ou região atual). É possível definir várias máscaras de discagem de emergência separando os valores com ponto e vírgulas. Por exemplo, 212;414. O comprimento máximo da cadeia é de 100 caracteres. Cada caractere precisa ser um dígito de 0 a 9.
        
        <div>
        

        > [!IMPORTANT]  
        > Certifique-se de que o valor de máscara de discagem especificado não seja igual a um número em um intervalo de linha de estacionamento de chamada. O roteamento do parque de chamadas terá precedência com a conversão de cadeia de discagem de emergência. Para ver os intervalos de o parque de chamadas existentes, clique em <STRONG>recursos de voz</STRONG> na barra de navegação à esquerda e clique em <STRONG>ligar para estacionamento</STRONG>. Para obter detalhes, consulte <A href="lync-server-2013-configure-phone-number-extensions-for-parking-calls.md">Configurar extensões de número de telefone para chamadas de estacionamento no Lync Server 2013</A>.

        
        </div>
    
      - **URI de notificação**   um ou mais URIs (Uniform Resource Identifiers) SIP a serem notificados quando uma chamada de emergência é feita. Por exemplo, o escritório de segurança da empresa pode ser notificado por uma mensagem instantânea sempre que uma chamada de emergência é feita. Se a localização do chamador estiver disponível, essa localização será incluída na notificação. Vários URIs SIP podem ser incluídos como uma lista separada por vírgulas. Por exemplo, "sip:security@litwareinc.com","sip:kmyer@litwareinc.com". As listas de distribuição são aceitas. A cadeia de cadeia de caracteres precisa ter de 1 a 256 caracteres e precisa começar com o prefixo "sip:". Antes de clicar no campo URI da notificação, um exemplo é exibido.
    
      - **URI da conferência**   o URI SIP, nesse caso, o número de telefone de terceiros que serão em conferência para qualquer chamada de emergência feita. Por exemplo, o Office de segurança da empresa pode receber uma chamada quando uma chamada de emergência é feita e ouvir ou participar dessa chamada (dependendo do valor fornecido no campo **modo de conferência** ). A cadeia de caracteres precisa ter de 1 a 256 caracteres e precisa começar com o prefixo sip:. Um exemplo é exibido até que você clique dentro desse campo.
    
      - **Modo**   de conferência se você especificar um valor no campo **URI de conferência** , o modo de **conferência** determinará se uma terceira parte pode participar da chamada ou somente pode ouvi-la. Especifique uma das seguintes opções:
        
          - **Unidirecional**   um terceiro só pode ouvir a conversa entre o chamador e o operador de PSAP.
        
          - **Bidirecional**   um terceiro pode ouvir e participar da chamada entre o chamador e o operador PSAP.

6.  Clique em **Confirmar**.
    
    <div>
    

    > [!IMPORTANT]  
    > Quando você cria uma política de usuário, inicialmente essa política não se aplica a nenhum usuário ou site de rede. Para aplicar a política a um usuário, clique em <STRONG>usuários</STRONG> na barra de navegação à esquerda. Localize o usuário ao qual você deseja aplicar a política. No menu <STRONG>Editar</STRONG>, clique em <STRONG>Exibir detalhes</STRONG>. Na página <STRONG>Editar usuário do Lync Server</STRONG> , selecione a lista de novos locais na lista suspensa <STRONG>política de localização</STRONG> e clique em <STRONG>confirmar</STRONG>.<BR>Para aplicar a política a um site de rede, clique em <STRONG>configuração de rede</STRONG> na barra de navegação à esquerda e, em seguida, clique em <STRONG>site</STRONG>. Localize o site de rede ao qual você deseja aplicar a política. No menu <STRONG>Editar</STRONG>, clique em <STRONG>Exibir detalhes</STRONG>. Em <STRONG>Editar site</STRONG>, selecione a nova política de localização na lista suspensa <STRONG>diretiva de local</STRONG> e clique em <STRONG>confirmar</STRONG>.

    
    </div>

</div>

<div>

## <a name="to-modify-a-location-policy-in-lync-server-control-panel"></a>Para modificar uma política de localização no painel de controle do Lync Server

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **configuração de rede** e, em seguida, clique em **política de localização**.

4.  Na página **política de localização** , selecione a política de localização que você deseja modificar.

5.  No menu **Editar**, clique em **Exibir detalhes**.

6.  Na página **Editar política de local** , modifique os campos conforme necessário (para obter detalhes, veja a etapa 5 nos procedimentos "para criar uma nova política de local" anteriormente neste tópico).

7.  Clique em **Confirmar**.

</div>

<div>

## <a name="see-also"></a>Confira também


[Excluindo uma política de localização no Lync Server 2013](lync-server-2013-deleting-a-location-policy.md)  


[Definindo a política de localização do Lync Server 2013](lync-server-2013-defining-the-location-policy.md)  


[Configurar extensões de número de telefone para chamadas com estacionamento no Lync Server 2013](lync-server-2013-configure-phone-number-extensions-for-parking-calls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

