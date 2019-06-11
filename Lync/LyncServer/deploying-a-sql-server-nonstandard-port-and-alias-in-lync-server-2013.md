---
title: Implantando porta não padrão e alias do SQL Server no Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying a SQL Server nonstandard port and alias in Lync Server 2013
ms:assetid: 2da92c1f-250e-407a-8651-fb2aec76aeb0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn776290(v=OCS.15)
ms:contentKeyID: 62634609
ms.date: 09/17/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 35365cbd43aa3bea9afe5cdd036bd3834fae5037
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836876"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-a-sql-server-nonstandard-port-and-alias-in-lync-server-2013"></a>Implantando porta não padrão e alias do SQL Server no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2015-09-16_

O Microsoft Lync Server 2013 oferece suporte ao uso de uma porta e alias não padrão no SQL Server. Usar uma porta não padrão do SQL Server e um alias aumenta a segurança e cria um ambiente mais flexível para a implantação do Lync. Estas etapas são apenas uma única etapa para a proteção adequada do ambiente do Lync Server 2013. Etapas adicionais devem ser seguidas para reduzir a superfície de ataque de uma implementação do Lync Server 2013.

O artigo a seguir descreve as etapas necessárias para configurar uma porta não padrão do SQL Server e alias no Lync Server 2013.

<div>

## <a name="deploying-a-sql-server-non-standard-port-and-alias-in-lync-server-2013"></a>Implantando uma porta e um alias não padrão do SQL Server no Lync Server 2013

O construtor de topologias do Lync Server 2013 oferece suporte ao uso de um alias do SQL Server como o FQDN (nome de domínio totalmente qualificado) em vez do FQDN do SQL Server atual ao configurar o Lync Server 2013. Isso permite que o FQDN real do SQL Server fique oculto de qualquer invasor mal-intencionado. Além disso, o uso de uma porta não padrão obscurece a porta real de qualquer invasor que esteja tentando atacar o banco de dados na porta padrão 1433, conforme mostrado na figura a seguir.

![Um hacker não sabe o número da porta a ser atacado.] (images/Dn776290.2f3923e0-2bdc-416b-a66b-bf56599eb14e(OCS.15).jpg "Um hacker não sabe o número da porta a ser atacado.")

Para ter êxito ao determinar que a porta do Lync Server 2013 está usando para se comunicar com o SQL Server, o invasor precisaria verificar todas as portas para obter as informações de porta. Uma verificação de porta por um invasor aumenta a probabilidade de que a segurança possa detectar e interromper a instrução. Além de adicionar maior segurança com uma porta não padrão, você também pode usar um alias do SQL Server para fornecer flexibilidade para a implantação. Isso é útil para reduzir as alterações de configuração em situações em que uma alteração de nome do SQL Server é necessária.

<div>


> [!NOTE]  
> O SQL Server oferece dois métodos de tolerância a falhas (clustering de failover e espelhamento). Os dois métodos de tolerância a falhas do SQL Server têm suporte usando uma porta não padrão do SQL Server e alias com o Lync Server 2013. Se o back-end do SQL Server usado pelo pool estiver em uma configuração espelhada, então o serviço do SQL browser nos servidores back-end do SQL Server deve estar em execução para que os servidores front-end se conectem ao banco de dados espelhado quando os bancos de dados tiverem failover para o SQL espelhado Servidor.



</div>

Ao configurar a conectividade de banco de dados do SQL Server no construtor de topologias ou ao usar o cmdlet Install-CsDatabase, não é possível definir explicitamente um número de porta não padrão do SQL Server e associá-lo a uma instância SQL. Para definir uma porta não padrão, você precisará usar os utilitários do SQL Server e do Windows Server.

Para configurar uma porta e um alias não padrão do SQL Server para uso com o Lync Server 2013, será necessário concluir três etapas principais. Estas etapas são:

  - Confirme se o Lync Server 2013 tem as atualizações mais recentes aplicadas.

  - Configurar a porta e o alias não padrão do SQL Server.

  - Configure o Lync Server 2013 com o alias do SQL Server usando o construtor de topologias.

  - Publique a topologia e verifique o banco de dados.

<div>

## <a name="confirm-that-lync-server-2013-has-the-latest-updates-applied"></a>Confirme se o Lync Server 2013 tem as atualizações mais recentes aplicadas

É importante manter atualizado o Lync Server 2013. Para verificar as atualizações e informações mais recentes sobre como aplicá-las, confira [atualizações para o Lync Server 2013](http://support.microsoft.com/kb/2809243).

</div>

<div>

## <a name="setup-the-sql-server-non-standard-port-and-alias"></a>Configurar a porta e o alias não padrão do SQL Server

A porta e o alias não padrão do SQL Server devem ser configurados na instância do banco de dados para que ele possa ser referenciado do construtor de topologias do Lync Server 2013. Para configurar uma porta e um alias não padrão do SQL Server, será necessário concluir três etapas principais. Estas etapas são as seguintes:

  - Altere os valores de protocolo TCP/IP padrão.

  - Criar e configurar um alias do SQL Server.

  - Criar um registro de recurso de nome canônico (CNAME) do sistema de nome de domínio (DNS).

**Modificar os valores de protocolo TCP/IP padrão**

1.  Selecione **Iniciar**e escolha **Gerenciador de configuração do SQL Server**, conforme mostrado na figura a seguir.
    
    ![O ícone do SQL Server Management Studio] (images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "O ícone do SQL Server Management Studio")

2.  No painel de navegação, escolha expandir a **instância do SQL Server**, escolha expandir a **configuração de rede do SQL Server**e escolha **protocolos \<para nome\>da instância**, conforme mostrado na figura a seguir.
    
    ![Navegar para as propriedades de TCP/IP] (images/Dn776290.3d7a964c-f17e-47fd-8f0c-535453da7fad(OCS.15).jpg "Navegar para as propriedades de TCP/IP")

3.  No painel direito, clique com o botão direito do mouse em **TCP/IP**e selecione **Propriedades**. A caixa de diálogo Propriedades de TCP/IP é exibida.

4.  Selecione a guia **endereços IP** . A guia endereços IP mostra todos os endereços IP ativos no servidor. Elas estão no formato IP1, IP2, até IPAll, conforme mostrado na figura a seguir.
    
    ![Abra as propriedades de TCP/IP.] (images/Dn776290.ed2fd70d-1836-4ebf-80fe-09191d96585e(OCS.15).jpg "Abra as propriedades de TCP/IP.")

5.  Desmarque o campo **portas TCP dinâmicas** para todos os endereços IP. Se o campo contiver um caractere zero, significará que o SQL Server está ouvindo portas dinâmicas. Certifique-se de que esses campos estejam limpos e não contenham zero.

6.  Para o endereço IP que o Lync Server usará para se conectar ao banco de dados, verifique se **habilitado** está definido como **Sim**, conforme mostrado na figura a seguir.
    
    ![Defina Enabled como Yes para o IP correto.] (images/Dn776290.7f818b91-0793-4594-8932-90447270fad9(OCS.15).jpg "Defina Enabled como Yes para o IP correto.")

7.  Na seção **IPAll** na parte inferior da caixa de diálogo, insira a porta desejada no campo **porta TCP** , conforme mostrado na figura a seguir. Neste exemplo, usamos a porta 50062, mas você pode usar qualquer porta entre o 49152 e o 65535. Estas são as portas atribuídas ao uso dinâmico e privado, e isso garante que você não entre em conflito com outras portas usadas na implantação do Lync Server 2013.
    
    ![Defina a porta na seção IPAll.] (images/Dn776290.b5af53e2-7961-4664-b586-3ca8f3a17f06(OCS.15).jpg "Defina a porta na seção IPAll.")

8.  Escolha **OK** para sair da caixa de diálogo Propriedades de TCP/IP.

9.  Reinicie a instância do SQL Server selecionando **Serviços do SQL Server** no painel esquerdo do Gerenciador de configuração do SQL Server. Em seguida, clique com o botão direito do mouse no **nome \<\> da instância do SQL Server** no painel direito e selecione **reiniciar**, conforme mostrado na figura a seguir.
    
    ![Redefina o serviço do SQL Server por exemplo.] (images/Dn776290.a965c8cf-f769-4b52-bb38-c48a438cf491(OCS.15).jpg "Redefina o serviço do SQL Server por exemplo.")

<div>


> [!IMPORTANT]  
> Certifique-se de atualizar as configurações do seu firewall para acomodar a nova porta do SQL Server.



</div>

**Criar e configurar um alias do SQL Server**

1.  Selecione **Iniciar**e escolha **Gerenciador de configuração do SQL Server**, conforme mostrado na figura a seguir.
    
    ![O ícone do SQL Server Management Studio] (images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "O ícone do SQL Server Management Studio")

2.  No painel esquerdo, escolha para expandir a **instância do SQL Server**, escolha expandir a **configuração de \<versão\> do SQL Native Client**e, em seguida, escolha **aliases**, conforme mostrado na figura a seguir.
    
    ![Aliases no Gerenciador de configuração do SQL Server.] (images/Dn776290.95341826-55d7-425f-ae19-d47d6668c5d8(OCS.15).jpg "Aliases no Gerenciador de configuração do SQL Server.")

3.  Clique com o botão direito do mouse em **alias**e selecione **novo alias..**..

4.  Digite o **nome do alias**, o **número da porta**, o **protocolo**e o **servidor**, conforme mostrado na figura a seguir.
    
    ![Criando um novo alias] (images/Dn776290.03653588-aecf-4fdd-b58a-95f5b372d478(OCS.15).jpg "Criando um novo alias")
    
    <div>
    

    > [!CAUTION]  
    > Certifique-se de digitar a mesma porta não padrão que você usou na etapa anterior, pois a porta do SQL Server estará ouvindo. Se um alias configurado estiver se conectando ao FQDN ou à instância errada do SQL Server, desabilite e habilite novamente o protocolo de rede associado. Isso limpa todas as informações de conexão armazenadas em cache e permite que o cliente se conecte corretamente.

    
    </div>

**Criar um registro de recurso CNAME de DNS**

1.  Entre no computador Gerenciando o DNS.

2.  Selecione **Iniciar**e escolha **Gerenciador de servidores**, conforme mostrado na figura a seguir.
    
    ![Abrindo o Gerenciador de servidores] (images/Dn776290.3e4bd8ad-2a65-4a05-af40-c8dd3583bc8f(OCS.15).jpg "Abrindo o Gerenciador de servidores")

3.  Escolha a lista suspensa **ferramentas** e selecione **DNS**, conforme mostrado na figura a seguir.
    
    ![Abrindo o DNS do Gerenciador de servidores.] (images/Dn776290.415e1da1-7c9a-4a4e-a896-ca34a76aaeff(OCS.15).jpg "Abrindo o DNS do Gerenciador de servidores.")

4.  No painel esquerdo, expanda o nó nome do servidor, expanda o nó de zonas de pesquisa direta e escolha o domínio relevante.

5.  Clique com o botão direito do mouse no domínio e selecione **novo alias (CNAME)...**, conforme mostrado na figura a seguir.
    
    ![Selecionando a opção para criar um novo alias CNAME] (images/Dn776290.abe66cca-b53c-427a-9094-1a59dc6840ca(OCS.15).jpg "Selecionando a opção para criar um novo alias CNAME")

6.  Digite o **nome do alias** e o **FQDN do SQL Server**, conforme mostrado na figura a seguir.
    
    ![Preenchendo a caixa de diálogo novo alias CNAME.] (images/Dn776290.dd0ebd2d-3407-4459-8bd9-2b389a7bc440(OCS.15).jpg "Preenchendo a caixa de diálogo novo alias CNAME.")

7.  Escolha **OK** para salvar o CNAME e exibi-lo no Gerenciador de DNS.

</div>

<div>

## <a name="validate-database-connectivity"></a>Validar a conectividade do banco de dados

Há muitas maneiras diferentes de verificar se ele está funcionando. Você deseja certificar-se de que o banco de dados do SQL Server está ouvindo na porta especificada usando o alias. Uma verificação rápida pode ser completada usando **** os comandos netstat e **Telnet** .

<div>


> [!NOTE]  
> O cliente Telnet é um recurso que vem com o Windows Server, mas que deve ser instalado. Um recurso do Windows Server pode ser instalado abrindo o Gerenciador do servidor e selecionando Adicionar funções e recursos no menu gerenciar.



</div>

**Usar netstat e Telnet para verificar a conectividade do banco de dados**

1.  Selecione **Iniciar**e digite **cmd** para abrir um prompt de comando.

2.  Digite **netstat-a-f**e confirme se o SQL Server está em execução com a porta correta, conforme mostrado na figura a seguir.
    
    ![Usando netstat para verificar a porta.] (images/Dn776290.4ff3a1b2-c5eb-4496-8be7-374c351fa027(OCS.15).jpg "Usando netstat para verificar a porta.")

3.  Digite **a \<\> \<porta \# do nome do alias Telnet** para confirmar a conexão com a instância do SQL Server. Se a conexão for bem-sucedida, o telnet será conectado e você não verá um erro. Isso mostra que a instância do SQL Server está ouvindo na porta correta com o alias correto. Se houver problemas para se conectar ao banco de dados do SQL Server, o Telnet mostrará um erro informando que a conexão não pode ser feita. Agora que você verificou a conectividade do banco de dados no servidor de banco de dados, é possível fazer a mesma coisa no Lync Server (na rede) e verificar se não há firewalls bloqueando o acesso ao longo do caminho.

</div>

<div>

## <a name="conclusion"></a>Conclusão

Após a configuração do alias do SQL Server, você pode usá-lo para criar uma topologia do Lync Server 2013 na ferramenta Topology Builder. Para obter mais informações sobre topologias, consulte [definindo e configurando a topologia no Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).

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

