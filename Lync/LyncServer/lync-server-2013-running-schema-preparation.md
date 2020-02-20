---
title: 'Lync Server 2013: executando a preparação do esquema'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Running schema preparation
ms:assetid: 9d02bdb1-ff29-417a-bcce-b068b31207d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412729(v=OCS.15)
ms:contentKeyID: 48184911
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b8336bdb881570c40900600c1eda3c3c17ffb614
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144447"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="running-active-directory-schema-preparation-in-lync-server-2013"></a>Executando a preparação do esquema do Active Directory no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-29_

Você pode usar os cmdlets de instalação ou do Shell de gerenciamento do Lync Server para preparar o esquema do Active Directory. O cmdlet que estende o esquema do Active Directory é **Install-CsAdServerSchema**.

<div>


> [!NOTE]  
> O cmdlet de preparação do esquema (<STRONG>Install-CsAdServerSchema</STRONG>) deve acessar o mestre de esquema, que exige que o serviço registro remoto esteja em execução e que a chave do registro remoto esteja habilitada. Se o serviço registro remoto não puder ser habilitado no mestre de esquema, você pode executar o cmdlet localmente no mestre de esquema. Para obter detalhes sobre o acesso remoto do registro, consulte o artigo 314837 da base de dados de conhecimento da Microsoft, "como gerenciar <A href="https://go.microsoft.com/fwlink/p/?linkid=125769">https://go.microsoft.com/fwlink/p/?linkId=125769</A>o acesso remoto ao registro" em.



</div>

Após a conclusão da preparação do esquema, verifique manualmente se a partição do esquema foi replicada antes de prosseguir para a preparação da floresta. Para obter detalhes, consulte [Verifying Active Directory Schema Replication in Lync Server 2013](lync-server-2013-verifying-schema-replication.md).

<div>

## <a name="to-use-setup-to-prepare-the-schema-of-the-current-forest"></a>Para usar a Instalação para preparar o esquema da floresta atual

1.  Faça logon em um servidor em sua floresta como membro do grupo Administradores de Esquema e com direitos de administrador no mestre de esquema.

2.  Na pasta ou mídia de instalação do Lync Server 2013, execute Setup. exe para iniciar o assistente de implantação.

3.  Se for solicitado que você instale o Microsoft Visual C++ Redistributable, clique em **Sim**.

4.  A caixa de diálogo instalação do Lync Server 2013 solicita um local para instalar os arquivos do Lync Server. Escolha o local padrão ou **Procure** um local de sua escolha e clique em **Instalar**.

5.  Na página Contrato de Licença, marque **Aceito os termos do contrato de licença** e clique em **OK**.

6.  O instalador instala os componentes principais do Lync Server.

7.  Quando o Assistente de Implantação estiver pronto, clique em **Preparar Active Directory** e espere que o estado da implantação seja determinado.

8.  Na **Etapa 1: Preparar Esquema**, clique em **Executar**.

9.  Na página **Preparar Esquema**, clique em **Avançar**.

10. Na página **Executando Comandos**, procure **Status da tarefa: Concluída** e clique em **Exibir Log**.

11. Na coluna **ação** , expanda **esquema Prep**, procure o ** \<\> ** resultado de execução de êxito no final de cada tarefa para verificar se a preparação do esquema foi concluída com êxito, feche o log e clique em **concluir**.

12. Aguarde a replicação do Active Directory ser concluída ou force a replicação.

13. Verifique manualmente se as alterações do esquema foram replicadas para todos os outros controladores de domínio. Para obter detalhes, consulte [Verifying Active Directory Schema Replication in Lync Server 2013](lync-server-2013-verifying-schema-replication.md).

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-schema-of-the-current-forest"></a>Para usar cmdlets para preparar o esquema da floresta atual

1.  Faça logon em um computador na floresta como um membro do grupo Administradores de Esquemas e com direitos de administrador no mestre de esquema.

2.  Instale os componentes principais do Lync Server da seguinte maneira:
    
    1.  Na pasta ou mídia de instalação do Lync Server 2013, execute Setup. exe para iniciar o assistente de implantação do Lync Server.
    
    2.  Se for solicitado que você instale o Microsoft Visual C++ Redistributable, clique em **Sim**.
    
    3.  A caixa de diálogo instalação do Lync Server 2013 solicita um local para instalar os arquivos do Lync Server. Escolha o local padrão ou **Procure** um local de sua escolha e clique em **Instalar**.
    
    4.  Na página Contrato de Licença, marque **Aceito os termos do contrato de licença** e clique em **OK**. O instalador instala os componentes principais do Lync Server 2013.

3.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

4.  Sejam
    
        Install-CsAdServerSchema [-Ldf <directory where the .ldf file is located>] 
    
    Se você não especificar o parâmetro ldf, o valor padrão será o caminho de instalação do Lync Server 2013 que é lido a partir do registro.
    
    Por exemplo:
    
        Install-CsAdServerSchema -Ldf "C:\Program Files\Microsoft Lync Server 2013\Deployment\Setup"

5.  Use o cmdlet a seguir para verificar se a preparação do esquema foi executada até o final.
    
        Get-CsAdServerSchema 
    
    Este cmdlet retorna um valor de **estado\_\_de\_versão do esquema atual** se a preparação do esquema tiver sido bem-sucedida.

6.  Aguarde a replicação do Active Directory ser concluída ou force a replicação.

7.  Verifique manualmente se as alterações do esquema foram replicadas para todos os outros controladores de domínio. Para obter detalhes, consulte [Verifying Active Directory Schema Replication in Lync Server 2013](lync-server-2013-verifying-schema-replication.md).

</div>

<div>

## <a name="see-also"></a>Confira também


[Verificando a replicação do esquema do Active Directory no Lync Server 2013](lync-server-2013-verifying-schema-replication.md)  


[Preparando o esquema do Active Directory no Lync Server 2013](lync-server-2013-preparing-the-active-directory-schema.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

