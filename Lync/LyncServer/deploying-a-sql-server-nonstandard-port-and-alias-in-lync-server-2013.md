---
title: Implantando uma porta e um alias não padrão do SQL Server no Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying a SQL Server nonstandard port and alias in Lync Server 2013
ms:assetid: 2da92c1f-250e-407a-8651-fb2aec76aeb0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn776290(v=OCS.15)
ms:contentKeyID: 62634609
ms.date: 09/17/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ef6082c4d2df6936557cf6f6c82a1d495888f55
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006417"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-a-sql-server-nonstandard-port-and-alias-in-lync-server-2013"></a>Implantando uma porta e um alias não padrão do SQL Server no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2015-09-16_

O Microsoft Lync Server 2013 suporta o uso de uma porta não padrão e um alias no SQL Server. Usar uma porta não padrão do SQL Server e um alias aumenta a segurança e cria um ambiente mais flexível para a implantação do Lync. Estas etapas são apenas uma única etapa de proteção adequada do seu ambiente do Lync Server 2013. Etapas adicionais devem ser seguidas para reduzir a superfície de ataque de uma implementação do Lync Server 2013.

O artigo a seguir descreve as etapas necessárias para configurar uma porta não padrão do SQL Server e alias no Lync Server 2013.

<div>

## <a name="deploying-a-sql-server-non-standard-port-and-alias-in-lync-server-2013"></a>Implantando uma porta e um alias não padrão do SQL Server no Lync Server 2013

O construtor de topologias do Lync Server 2013 suporta o uso de um alias do SQL Server como o FQDN (nome de domínio totalmente qualificado) em vez do FQDN do SQL Server atual ao configurar o Lync Server 2013. Isso permite que o FQDN do SQL Server real fique oculto de qualquer invasor mal-intencionado. Além disso, o uso de uma porta não-padrão obscurece a porta real de qualquer invasor que esteja tentando atacar o banco de dados na porta 1433 padrão, conforme mostrado na figura a seguir.

![Um hacker não sabe o número da porta a ser atacado.](images/Dn776290.2f3923e0-2bdc-416b-a66b-bf56599eb14e(OCS.15).jpg "Um hacker não sabe o número da porta a ser atacado.")

Para ter êxito ao determinar que a porta que o Lync Server 2013 está usando para se comunicar com o SQL Server, o invasor precisaria verificar todas as portas para obter as informações de porta. Uma verificação de porta por um invasor aumenta as chances de que a segurança possa detectar e interromper a instrução. Além de adicionar maior segurança a uma porta não padrão, você também pode usar um alias do SQL Server para oferecer flexibilidade para a implantação. Isso é útil para reduzir as alterações de configuração em situações em que é necessário alterar o nome do SQL Server.

<div>


> [!NOTE]  
> O SQL Server fornece dois métodos de tolerância a falhas (clustering de failover e espelhamento). Os métodos de tolerância a falhas do SQL Server têm suporte usando uma porta não padrão do SQL Server e alias com o Lync Server 2013. Se o back-end do SQL Server usado pelo pool estiver em uma configuração espelhada, então o SQL browser Service nos servidores backend do SQL Server deverá estar em execução para que os servidores front-end se conectem ao banco de dados espelhado quando os bancos de dados tiverem failover para o SQL espelhado Do.



</div>

Ao configurar a conectividade de banco de dados do SQL Server a partir do construtor de topologias, ou ao usar o cmdlet Install-CsDatabase, não é possível definir explicitamente um número de porta não padrão do SQL Server e associá-lo a uma instância SQL. Para definir uma porta não padrão, você precisará usar os utilitários do SQL Server e do Windows Server.

Para configurar uma porta e um alias não padrão do SQL Server para uso com o Lync Server 2013, será necessário concluir três etapas principais. Essas etapas são:

  - Confirme se o Lync Server 2013 tem as atualizações mais recentes aplicadas.

  - Configure a porta e o alias não padrão do SQL Server.

  - Configure o Lync Server 2013 com o alias do SQL Server usando o construtor de topologias.

  - Publique a topologia e verifique o banco de dados.

<div>

## <a name="confirm-that-lync-server-2013-has-the-latest-updates-applied"></a>Confirmar se o Lync Server 2013 tem as atualizações mais recentes aplicadas

É importante manter atualizado o Lync Server 2013. Para verificar as atualizações e informações mais recentes sobre como aplicá-las, consulte [atualizações para o Lync Server 2013](http://support.microsoft.com/kb/2809243).

</div>

<div>

## <a name="setup-the-sql-server-non-standard-port-and-alias"></a>Configurar a porta e o alias não padrão do SQL Server

A porta e o alias não padrão do SQL Server devem ser configurados na instância do banco de dados antes de ser referenciado do construtor de topologias do Lync Server 2013. Para configurar uma porta e um alias não padrão do SQL Server, você precisará concluir três etapas principais. As etapas são as seguintes:

  - Altere os valores de protocolo TCP/IP padrão.

  - Criar e configurar um alias do SQL Server.

  - Criar um registro de recurso de nome canônico (CNAME) do sistema de nome de domínio (DNS).

**Modificar os valores de protocolo TCP/IP padrão**

1.  Selecione **Iniciar**e escolha **Gerenciador de configuração do SQL Server**, conforme mostrado na figura a seguir.
    
    ![O ícone do SQL Server Management Studio](images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "O ícone do SQL Server Management Studio")

2.  No painel de navegação, escolha expandir a **instância do SQL Server**, optar por expandir a **configuração de rede do SQL Server**e escolher **protocolos para\>nome de \<instância**, conforme mostrado na figura a seguir.
    
    ![Navegar para propriedades de TCP/IP](images/Dn776290.3d7a964c-f17e-47fd-8f0c-535453da7fad(OCS.15).jpg "Navegar para propriedades de TCP/IP")

3.  No painel direito, clique com o botão direito do mouse em **TCP/IP**e selecione **Propriedades**. A caixa de diálogo Propriedades de TCP/IP é exibida.

4.  Selecione a guia **endereços IP** . A guia endereços IP mostra todos os endereços IP ativos no servidor. Eles estão no formato IP1, IP2, até IPAll, conforme mostrado na figura a seguir.
    
    ![Abra as propriedades de TCP/IP.](images/Dn776290.ed2fd70d-1836-4ebf-80fe-09191d96585e(OCS.15).jpg "Abra as propriedades de TCP/IP.")

5.  Desmarque o campo **portas dinâmicas TCP** para todos os endereços IP. Se o campo contiver um caractere zero, significa que o SQL Server está escutando nas portas dinâmicas. Certifique-se de que esses campos estejam desmarcados e não contenham zero.

6.  Para o endereço IP que o Lync Server usará para se conectar ao banco de dados, verifique se **habilitado** está definido como **Sim**, conforme mostrado na figura a seguir.
    
    ![Defina habilitado como Sim para o IP correto.](images/Dn776290.7f818b91-0793-4594-8932-90447270fad9(OCS.15).jpg "Defina habilitado como Sim para o IP correto.")

7.  Na seção **IPAll** na parte inferior da caixa de diálogo, digite a porta desejada no campo **porta TCP** , conforme mostrado na figura a seguir. Neste exemplo, usamos a porta 50062, mas você pode usar qualquer porta entre 49152 e 65535. Estas são as portas atribuídas ao uso dinâmico e privado, e isso garante que você não entre em conflito com outras portas que estão sendo usadas na implantação do Lync Server 2013.
    
    ![Set port na seção IPAll.](images/Dn776290.b5af53e2-7961-4664-b586-3ca8f3a17f06(OCS.15).jpg "Set port na seção IPAll.")

8.  Escolha **OK** para sair da caixa de diálogo Propriedades de TCP/IP.

9.  Reinicie a instância do SQL Server selecionando **Serviços do SQL Server** no painel esquerdo do SQL Server Configuration Manager. Em seguida, clique com o botão direito do mouse no **nome \<\> da instância do SQL Server** no painel direito e selecione **reiniciar**, conforme mostrado na figura a seguir.
    
    ![Redefina o serviço do SQL Server para a instância.](images/Dn776290.a965c8cf-f769-4b52-bb38-c48a438cf491(OCS.15).jpg "Redefina o serviço do SQL Server para a instância.")

<div>


> [!IMPORTANT]  
> Certifique-se de atualizar suas configurações de firewall para acomodar a nova porta do SQL Server.



</div>

**Criar e configurar um alias do SQL Server**

1.  Selecione **Iniciar**e escolha **Gerenciador de configuração do SQL Server**, conforme mostrado na figura a seguir.
    
    ![O ícone do SQL Server Management Studio](images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "O ícone do SQL Server Management Studio")

2.  No painel esquerdo, escolha para expandir a **instância do SQL Server**, opte por expandir a **configuração \<da\> versão do SQL Native Client**e, em seguida, escolha **aliases**, conforme mostrado na figura a seguir.
    
    ![Aliases no SQL Server Configuration Manager.](images/Dn776290.95341826-55d7-425f-ae19-d47d6668c5d8(OCS.15).jpg "Aliases no SQL Server Configuration Manager.")

3.  Clique com o botão direito do mouse em **aliases**e selecione **novo alias...**.

4.  Insira o **nome do alias**, o **número da porta**, o **protocolo**e o **servidor**, conforme mostrado na figura a seguir.
    
    ![Criar um novo alias](images/Dn776290.03653588-aecf-4fdd-b58a-95f5b372d478(OCS.15).jpg "Criar um novo alias")
    
    <div>
    

    > [!CAUTION]  
    > Certifique-se de inserir a mesma porta não padrão que você usou na etapa anterior, pois esta é a porta que o SQL Server estará escutando. Se um alias configurado estiver se conectando ao FQDN do SQL Server ou à instância errada, desabilite e ative novamente o protocolo de rede associado. Isso limpa todas as informações de conexão armazenadas em cache e permite que o cliente se conecte corretamente.

    
    </div>

**Criar um registro de recurso CNAME de DNS**

1.  Entre no computador Gerenciando o DNS.

2.  Selecione **Iniciar**e escolha **Gerenciador do servidor**, conforme mostrado na figura a seguir.
    
    ![Abrir o Gerenciador do servidor](images/Dn776290.3e4bd8ad-2a65-4a05-af40-c8dd3583bc8f(OCS.15).jpg "Abrir o Gerenciador do servidor")

3.  Escolha as **ferramentas** suspensas e selecione **DNS**, conforme mostrado na figura a seguir.
    
    ![Abrir o DNS no Gerenciador do servidor.](images/Dn776290.415e1da1-7c9a-4a4e-a896-ca34a76aaeff(OCS.15).jpg "Abrir o DNS no Gerenciador do servidor.")

4.  No painel esquerdo, expanda o nó nome do servidor, expanda o nó zonas de pesquisa direta e escolha o domínio relevante.

5.  Clique com o botão direito do mouse no domínio e selecione **novo alias (CNAME)...**, conforme mostrado na figura a seguir.
    
    ![Selecionar a opção para criar um novo alias CNAME](images/Dn776290.abe66cca-b53c-427a-9094-1a59dc6840ca(OCS.15).jpg "Selecionar a opção para criar um novo alias CNAME")

6.  Insira o **nome do alias** e o **FQDN do SQL Server**, conforme mostrado na figura a seguir.
    
    ![Preenchendo a caixa de diálogo novo alias CNAME.](images/Dn776290.dd0ebd2d-3407-4459-8bd9-2b389a7bc440(OCS.15).jpg "Preenchendo a caixa de diálogo novo alias CNAME.")

7.  Escolha **OK** para salvar o CNAME e exibi-lo no Gerenciador de DNS.

</div>

<div>

## <a name="validate-database-connectivity"></a>Validar conectividade de banco de dados

Há várias maneiras diferentes de se certificar de que ele está funcionando. Você deseja certificar-se de que o banco de dados do SQL Server está escutando na porta especificada usando o alias. Uma verificação rápida pode ser concluída usando os comandos **netstat** e **Telnet** .

<div>


> [!NOTE]  
> O cliente Telnet é um recurso que acompanha o Windows Server, mas que deve ser instalado. Um recurso do Windows Server pode ser instalado ao abrir o Gerenciador do servidor e selecionar Adicionar funções e recursos no menu gerenciar.



</div>

**Usar netstat e Telnet para verificar a conectividade do banco de dados**

1.  Selecione **Iniciar**e digite **cmd** para abrir um prompt de comando.

2.  Digite **netstat-a-f**e confirme se o SQL Server está sendo executado com a porta correta, conforme mostrado na figura a seguir.
    
    ![Usando netstat para verificar Port.](images/Dn776290.4ff3a1b2-c5eb-4496-8be7-374c351fa027(OCS.15).jpg "Usando netstat para verificar Port.")

3.  Digite **porta \< \# de nome\> \<de alias Telnet** para confirmar a conexão com a instância do SQL Server. Se a conexão for bem-sucedida, o telnet será conectado e você não verá um erro. Isso mostra que a instância do SQL Server está escutando na porta correta com o alias correto. Se houver um problema de conexão com o banco de dados do SQL Server, o Telnet mostrará um erro informando que a conexão não pode ser feita. Agora que você verificou a conectividade do banco de dados no servidor de banco de dados, é possível fazer o mesmo com o Lync Server (pela rede) e verificar se não há firewalls bloqueando o acesso ao longo do caminho.

</div>

<div>

## <a name="conclusion"></a>Conclusão

Depois que o alias do SQL Server tiver sido configurado, você poderá usá-lo para criar uma topologia do Lync Server 2013 na ferramenta Construtor de topologias. Para obter mais informações sobre topologias, consulte [definindo e configurando a topologia no Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).

</div>

</div>

<div>

## <a name="see-also"></a>Confira também


[Microsoft Lync Server 2013](microsoft-lync-server-2013.md) 
[planejando a segurança no Lync Server 2013](lync-server-2013-planning-for-security.md)  
[Definindo e configurando a topologia no Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md)  
[Implantando o Lync Server 2013](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

