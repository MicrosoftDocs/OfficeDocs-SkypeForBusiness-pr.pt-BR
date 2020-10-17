---
title: 'Lync Server 2013: Criando ou modificando uma política de local'
description: 'Lync Server 2013: Criando ou modificando uma política de local.'
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
ms.openlocfilehash: ba097ddb6e4ca8515c1eb33ae9d7e033821aef31
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562997"
---
# <a name="creating-or-modifying-a-location-policy-in-lync-server-2013"></a>Criando ou modificando uma política de local no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-11-01_

No Lync Server 2013, você pode usar a política de local para aplicar configurações relacionadas à funcionalidade avançada 9-1-1 (E9-1-1) e às configurações de local para usuários ou contatos. A política de local determina se o usuário está habilitado para o E9-1-1 e, se estiver, qual vai ser o comportamento de uma chamada de emergência. Por exemplo, é possível usar a política de local para definir o número que constitui uma chamada de emergência (911 nos Estados Unidos), se a segurança da empresa deve ser automaticamente notificada e como a chamada é roteada.

Você pode configurar políticas de local no painel de controle de **rede** do Lync Server 2013. No painel de controle do Lync Server, você pode exibir, criar, modificar ou excluir políticas de local. Use os procedimentos desta seção para criar ou modificar uma política de local. Para obter detalhes sobre como excluir políticas de local, consulte [excluindo uma política de local no Lync Server 2013](lync-server-2013-deleting-a-location-policy.md).

No Lync Server 2013, você pode substituir a quantidade de tempo padrão entre as solicitações do cliente para uma atualização de local do serviço de informações de local. O valor padrão é de 4 horas. Use o cmdlet **set-CsLocationPolicy** com o parâmetro LocationRefreshInterval para substituir o valor padrão.

<div>

## <a name="to-create-a-new-location-policy-in-lync-server-control-panel"></a>Para criar uma nova política de local no painel de controle do Lync Server

1.  A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **Configuração de rede** e clique em **Política de local**.

4.  Na página **política de local** , clique em **novo** e selecione o tipo de política que você deseja criar:
    
      - Para criar uma política de site, clique em **política de site**. Em **selecionar um site**, escolha o site para o qual você deseja aplicar a política e clique em **OK**. Na página **nova política de local** , o **campo escopo** contém o valor **site**e o campo **nome** contém o nome do site escolhido. Não é possível modificar nenhum desses campos. Uma política de site é automaticamente aplicada a todos os usuários no site especificado e substitui a política global desses usuários.
    
      - Para criar uma **política de usuário**, clique em **política de usuário**. Na **nova política de local**, o campo **escopo** contém o valor **usuário**. Não é possível modificar esse valor. No campo **nome** , digite o nome que você deseja dar a essa política. Uma política de usuário não se aplica automaticamente a nenhum usuário. Após criar a política de usuário, você deve conceder manualmente a política aos usuários ou sites de rede aos quais deseja aplicar a política.

5.  Preencha os campos restantes da seguinte maneira:
    
      - **Habilitar serviços**     de emergência avançados Marque esta caixa de seleção para habilitar os usuários associados a essa política para E9-1-1. Quando os serviços de emergência estiverem habilitados, os clientes do Lync Server recuperarão informações de local no registro e incluirão as informações quando uma chamada de emergência for feita.
    
      - **Local**     Especifique um dos seguintes valores:
        
          - **Necessárias**     O usuário será solicitado a inserir informações de local quando o cliente se registrar em um novo local. O usuário pode recusar o aviso, sem digitar qualquer informação. Se as informações forem inseridas, uma chamada de emergência será atendida primeiro pelo provedor de serviços de emergência para verificar o local antes de ser roteado para o operador PSAP (ponto de resposta de segurança pública) (ou seja, o operador 911).
        
          - **Não obrigatório**     O usuário não será solicitado a fornecer um local. Quando uma chamada é feita sem informações de local, o provedor de serviços de emergência responderá à chamada e solicitará um local.
        
          - **Isenção**     Essa opção é o mesmo que o **necessário** , exceto pelo fato de que o usuário não pode ignorar a solicitação sem inserir informações de local. O usuário ainda pode concluir uma chamada de emergência, mas nenhuma outra chamada pode ser concluída sem inserir as informações. Além disso, o texto de aviso de isenção de responsabilidade será exibido para o usuário que poderá alertá-los sobre as conseqüências de declínio para inserir informações de local. Para definir o texto de aviso de isenção de responsabilidade, você deve usar o Shell de gerenciamento do Lync Server para executar o cmdlet **set-CsLocationPolicy** ou o cmdlet **New-CsLocationPolicy** com o parâmetro EnhancedEmergencyServiceDisclaimer. Para obter detalhes, consulte [set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsLocationPolicy) ou [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsLocationPolicy) na documentação do Shell de gerenciamento do Lync Server.
            
            <div>
            

            > [!NOTE]  
            > No Lync Server 2013, você pode usar a política de local para definir avisos de isenção de responsabilidade diferentes para localidades diferentes ou diferentes conjuntos de usuários, ao contrário do Lync Server 2010 onde você pode especificar apenas um aviso de isenção global para toda a organização.

            
            </div>
    
      - **Usar local somente**     para serviços de emergência O Lync pode usar informações de local por vários motivos (por exemplo, para notificar os colegas do seu local atual). Marque essa caixa de seleção para garantir que as informações de local estejam disponíveis somente para uso com uma chamada de emergência.
    
      - **Uso**     de PSTN O uso da PSTN (rede telefônica pública comutada) que será usado para determinar qual rota de voz será usada para rotear chamadas de emergência de clientes usando esse perfil. A rota associada a esse uso deve apontar para um tronco SIP dedicado a chamadas de emergência ou a um gateway de Emergency Location Identification Number (ELIN) que encaminha as chamadas de emergência ao Public Safety Answering Point (PSAP) mais próximo.
    
      - Número de discagem de **emergência**     O número discado para acessar os serviços de emergência. Nos Estados Unidos, esse valor é 911. A cadeia de caracteres deve ser composta pelos dígitos 0 a 9 e pode ter entre um e dez dígitos de comprimento.
    
      - Máscara de discagem de **emergência**     Um número que você deseja converter para o valor do número de discagem de emergência quando for discado. Por exemplo, se você inserir um valor de 212 neste campo e o campo número de discagem de emergência tiver um valor de 911, se um usuário discar 212 a chamada será feita a 911. Isso permite a discagem de números de emergência alternativos e ainda assim acessar os serviços de emergência (por exemplo, se alguém de um país ou região com um número de emergência diferente tenta discar o número desse país ou região em vez do número para o país ou região atual). É possível definir múltiplas máscaras de discagem de emergência separando os valores com ponto e vírgulas. Por exemplo, 212;414. O comprimento máximo da cadeia de caracteres é 100. Cada caractere deve ser um dígito entre 0 e 9.
        
        <div>
        

        > [!IMPORTANT]  
        > Garanta que o valor da máscara de discagem especificado não seja igual a um número no intervalo da órbita de estacionamento de chamadas. O roteamento do estacionamento de chamadas terá precedência sobre a conversão de cadeias de caracteres de discagem de emergência. Para ver os intervalos de órbita de estacionamento de chamada existentes, clique em <STRONG>recursos de voz</STRONG> na barra de navegação esquerda e clique em <STRONG>estacionamento de chamada</STRONG>. Para obter detalhes, consulte <A href="lync-server-2013-configure-phone-number-extensions-for-parking-calls.md">Configure Phone Number Extensions for estacionating calls in Lync Server 2013</A>.

        
        </div>
    
      - **URI**     de notificação Um ou mais URIs (identificadores de recursos uniformes) SIP a serem notificados quando uma chamada de emergência for feita. Por exemplo, o escritório de segurança da empresa poderia ser avisado, por meio de uma mensagem instantânea, sempre que ocorrer uma chamada de emergência. Se a localização do chamador estiver disponível, ela será incluída na notificação. Vários URIs do SIP podem ser incluídos como uma lista separada por vírgulas. Por exemplo, "sip:security@litwareinc.com","sip:kmyer@litwareinc.com". As listas de distribuição são suportadas. A string precisa ter de 1 a 256 caracteres e precisa começar com o prefixo "sip:". Antes de clicar no campo URI de notificação, um exemplo é exibido.
    
      - **URI**     de conferência O URI SIP, nesse caso, o número de telefone de um terceiro que será conferência em todas as chamadas de emergência feitas. Por exemplo, o escritório de segurança da empresa pode receber uma chamada quando uma chamada de emergência é feita e ouvir ou participar dessa chamada (dependendo do valor fornecido no campo **modo de conferência** ). A cadeia de caracteres deve ter entre um e 256 caracteres de comprimento e deve começar com o prefixo sip:. Um exemplo é exibido até que você clique dentro desse campo.
    
      - **Modo**     de conferência Se você especificar um valor no campo **URI de conferência** , o **modo de conferência** determinará se um terceiro pode participar da chamada ou só poderá escutar. Especifique uma das seguintes opções:
        
          - **Unidirecional**     Uma terceira parte só pode ouvir a conversa entre o chamador e o operador PSAP.
        
          - **Bidirecional**     Um terceiro pode ouvir e participar da chamada entre o chamador e o operador PSAP.

6.  Clique em **Confirmar**.
    
    <div>
    

    > [!IMPORTANT]  
    > Ao criar uma política de usuário, inicialmente essa diretiva não se aplica a usuários ou sites de rede. Para aplicar a política a um usuário, clique em <STRONG>usuários</STRONG> na barra de navegação à esquerda. Localize o usuário ao qual você deseja aplicar a política. No painel <STRONG>Ações</STRONG>, clique em <STRONG>Mostrar detalhes</STRONG>. Na página <STRONG>Editar usuário do Lync Server</STRONG> , selecione a política novo local na lista suspensa <STRONG>política de local</STRONG> e clique em <STRONG>confirmar</STRONG>.<BR>Para aplicar a política a um site de rede, clique em <STRONG>configuração de rede</STRONG> , na barra de navegação esquerda, e clique em <STRONG>site</STRONG>. Localize o site de rede ao qual você deseja aplicar a política. No painel <STRONG>Ações</STRONG>, clique em <STRONG>Mostrar detalhes</STRONG>. Em <STRONG>Editar site</STRONG>, selecione a nova política de local na lista suspensa <STRONG>política de local</STRONG> e clique em <STRONG>confirmar</STRONG>.

    
    </div>

</div>

<div>

## <a name="to-modify-a-location-policy-in-lync-server-control-panel"></a>Para modificar uma política de local no painel de controle do Lync Server

1.  A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **Configuração de rede** e clique em **Política de local**.

4.  Na página **Política de local**, selecione a política de local que você quer modificar.

5.  No menu **Editar**, clique em **Mostrar detalhes**.

6.  Na página **Editar política de local** , modifique os campos conforme necessário (para obter detalhes, confira a etapa 5 no procedimento "para criar uma nova política de local", anteriormente neste tópico).

7.  Clique em **Confirmar**.

</div>

<div>

## <a name="see-also"></a>Confira também


[Excluindo uma política de local no Lync Server 2013](lync-server-2013-deleting-a-location-policy.md)  


[Definir a política de local para o Lync Server 2013](lync-server-2013-defining-the-location-policy.md)  


[Configurar extensões de número de telefone para estacionamento de chamadas no Lync Server 2013](lync-server-2013-configure-phone-number-extensions-for-parking-calls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

