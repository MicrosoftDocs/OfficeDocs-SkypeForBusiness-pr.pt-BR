---
title: 'Lync Server 2013: Executando preparação de esquema'
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
ms.openlocfilehash: 06b02981e9baa589801839c8fd8c871ae35b0dde
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765039"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="running-active-directory-schema-preparation-in-lync-server-2013"></a>Executando preparação de esquema de Active Directory no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-29_

Você pode usar os cmdlets do Shell de gerenciamento do Lync Server e do setup para preparar o esquema do Active Directory. O cmdlet que estende o esquema do Active Directory é **install-CsAdServerSchema**.

<div>


> [!NOTE]  
> O cmdlet de preparação do esquema (<STRONG>install-CsAdServerSchema</STRONG>) deve acessar o mestre de esquema, que requer que o serviço do registro remoto esteja em execução e que a chave do registro remoto esteja habilitada. Se o serviço de registro remoto não puder ser habilitado no mestre de esquema, você poderá executar o cmdlet localmente no mestre de esquema. Para obter detalhes sobre o acesso remoto ao registro, consulte o artigo 314837 da base de dados de conhecimento Microsoft, "como gerenciar o <A href="http://go.microsoft.com/fwlink/p/?linkid=125769">http://go.microsoft.com/fwlink/p/?linkId=125769</A>acesso remoto ao registro".



</div>

Depois de concluir a preparação do esquema, verifique manualmente se a partição do esquema foi replicada antes de prosseguir com a preparação da floresta. Para obter detalhes, consulte [verificando a replicação de esquema do Active Directory no Lync Server 2013](lync-server-2013-verifying-schema-replication.md).

<div>

## <a name="to-use-setup-to-prepare-the-schema-of-the-current-forest"></a>Para usar a instalação para preparar o esquema da floresta atual

1.  Faça logon em um servidor na sua floresta como membro do grupo Administradores de esquemas e com direitos de administrador no mestre de esquema.

2.  Na pasta de instalação ou mídia do Lync Server 2013, execute Setup. exe para iniciar o assistente de implantação.

3.  Se você for solicitado a instalar o Microsoft Visual C++ Redistributable, clique em **Sim**.

4.  A caixa de diálogo instalação do Lync Server 2013 solicita um local para instalar os arquivos do Lync Server. Escolha o local padrão ou **navegue** até um local de sua escolha e clique em **instalar**.

5.  Na página contrato de licença, marque **a opção aceito os termos do contrato de licença**e clique em **OK**.

6.  O instalador instala os componentes principais do Lync Server.

7.  Quando o assistente de implantação estiver pronto, clique em **preparar o Active Directory**e aguarde o estado de implantação ser determinado.

8.  Na **etapa 1: preparar o esquema**, clique em **executar**.

9.  Na página **preparar esquema** , clique em **Avançar**.

10. Na página **Executando Comandos**, procure por **Status da tarefa: Concluída** e clique em **Exibir Log**.

11. Na coluna **Action (ação** ), expanda **Schema prep**, procure o resultado da ** \<execução Success\> ** no final de cada tarefa para verificar se a preparação do esquema foi concluída com êxito, feche o log e clique em **concluir**.

12. Aguarde a conclusão da replicação do Active Directory ou force a replicação.

13. Verifique manualmente se as alterações de esquema foram duplicadas para todos os outros controladores de domínio. Para obter detalhes, consulte [verificando a replicação de esquema do Active Directory no Lync Server 2013](lync-server-2013-verifying-schema-replication.md).

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-schema-of-the-current-forest"></a>Usar cmdlets para preparar o esquema da floresta atual

1.  Faça logon em um computador na floresta como membro do grupo Administradores de esquemas e com direitos de administrador no mestre de esquema.

2.  Instale os componentes principais do Lync Server da seguinte maneira:
    
    1.  Na pasta de instalação ou mídia do Lync Server 2013, execute Setup. exe para iniciar o assistente de implantação do Lync Server.
    
    2.  Se você for solicitado a instalar o Microsoft Visual C++ Redistributable, clique em **Sim**.
    
    3.  A caixa de diálogo instalação do Lync Server 2013 solicita um local para instalar os arquivos do Lync Server. Escolha o local padrão ou **navegue** até um local de sua escolha e clique em **instalar**.
    
    4.  Na página contrato de licença, marque **a opção aceito os termos do contrato de licença**e clique em **OK**. O instalador instala os componentes principais do Lync Server 2013.

3.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

4.  Execute:
    
        Install-CsAdServerSchema [-Ldf <directory where the .ldf file is located>] 
    
    Se você não especificar o parâmetro ldf, o valor padrão será o caminho de instalação do Lync Server 2013 lido do registro.
    
    Por exemplo:
    
        Install-CsAdServerSchema -Ldf "C:\Program Files\Microsoft Lync Server 2013\Deployment\Setup"

5.  Use o cmdlet a seguir para verificar se a conclusão da preparação do esquema foi concluída.
    
        Get-CsAdServerSchema 
    
    Esse cmdlet retorna um valor de **estado\_\_de\_versão do esquema atual** se a preparação do esquema foi bem-sucedida.

6.  Aguarde a conclusão da replicação do Active Directory ou force a replicação.

7.  Verifique manualmente se as alterações de esquema foram duplicadas para todos os outros controladores de domínio. Para obter detalhes, consulte [verificando a replicação de esquema do Active Directory no Lync Server 2013](lync-server-2013-verifying-schema-replication.md).

</div>

<div>

## <a name="see-also"></a>Confira também


[Verificando a replicação de esquema do Active Directory no Lync Server 2013](lync-server-2013-verifying-schema-replication.md)  


[Preparando o esquema do Active Directory no Lync Server 2013](lync-server-2013-preparing-the-active-directory-schema.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

