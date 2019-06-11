---
title: 'Lync Server 2013: Configurando um proxy inverso para descoberta automática'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring a reverse proxy for Autodiscover
ms:assetid: 1e3c3cc2-fe55-408b-99c4-c6e0a9252689
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945619(v=OCS.15)
ms:contentKeyID: 51541456
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5445a9ce81835863b610ef32ecc51ccac5331c3f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836301"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-reverse-proxy-for-autodiscover-in-lync-server-2013"></a>Configurando um proxy inverso para descoberta automática no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-12-12_

A descoberta automática e o suporte de clientes que usam a descoberta automática exigem a modificação de uma regra de publicação na Web existente ou a criação de uma nova regra de publicação na Web para o proxy reverso. A modificação ou criação de uma nova regra de publicação não depende da decisão de atualizar ou não atualizar as listas de nomes alternativos de entidades nos certificados de proxy reverso.

Se você decidir usar HTTPS para solicitações iniciais de serviço de descoberta automática do Lync Server 2013 e atualizar as listas de nomes alternativos de entidades nos certificados de proxy reverso, será necessário atribuir o certificado público atualizado ao ouvinte SSL (Secure Sockets Layer) em seu proxy reverso. A atualização necessária para o certificado externo (público) incluirá a entrada de nome alternativo (SAN) do assunto para lyncdiscover. \<nome\>do domínio. Em seguida, você precisará modificar o ouvinte existente para os serviços Web externos ou criar uma nova regra de publicação na Web para a URL do serviço de descoberta automática externa, por exemplo, **lyncdiscover.contoso.com**. Se você ainda não tiver uma regra de publicação na Web para a URL externa de serviços Web do Lync Server 2013 para seu pool de front-ends e pool de directors (se você tiver implantado directors), também precisará publicar uma regra para isso.

<div>


> [!NOTE]  
> A regra de publicação de proxy reverso e a escuta podem atender tanto os serviços Web externos quanto o serviço de descoberta automática, desde que o certificado atribuído ao ouvinte contenha o nome da entidade e os nomes alternativos de assunto necessários para ambos. Para obter detalhes sobre a configuração padrão do ouvinte da Web e da regra de publicação, consulte Configurando <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">servidores proxy reverso para o Lync Server 2013</A> para obter mais detalhes.



</div>

Se você decidir usar HTTP para solicitações de serviço de descoberta automática iniciais para que você não precise atualizar nomes alternativos de entidades para o proxy reverso, será necessário criar ou modificar uma regra de publicação na Web para a porta 80.

Os procedimentos desta seção descrevem como criar ou modificar as regras de publicação na Web no Microsoft Forefront Threat Management Gateway 2010 para descoberta automática.

<div>


> [!NOTE]  
> Esses procedimentos pressupõem que você tenha instalado a edição padrão do Forefront Threat Management Gateway (TMG) 2010. Se você estiver usando outro proxy reverso, os procedimentos serão similares, mas precisarão ser mapeados para a documentação do produto de terceiros.



</div>

<div>

## <a name="to-create-a-web-publishing-rule-for-the-external-autodiscover-url"></a>Para criar uma regra de publicação na Web para a URL de descoberta automática externa

1.  Clique em **Iniciar**, aponte para **programas**, aponte para **Microsoft Forefront TMG**e clique em **Gerenciamento do Forefront TMG**.

2.  No painel esquerdo, expanda **ServerName**, clique com o botão direito do mouse em **política de firewall**, aponte para **novo**e clique em regra de **publicação de site da Web**.

3.  Na página **Bem-vindo à nova regra de publicação na Web** , digite um nome para exibição para a nova regra de publicação (por exemplo, LyncDiscoveryURL).

4.  Na página **Selecionar ação da regra** , selecione **permitir**.

5.  Na página **tipo de publicação** , selecione **publicar um único site da Web ou um balanceador de carga**.

6.  Na página **segurança de conexão do servidor** , selecione **usar SSL para se conectar ao servidor Web ou ao farm de servidores publicado**.

7.  Na página **detalhes da publicação interna** , em **nome do site interno**, digite o nome de domínio totalmente qualificado (FQDN) do seu pool de diretor (por exemplo, lyncdir01. contoso. local). Se você estiver criando uma regra para a URL de serviços Web externos no pool de front-ends, digite o FQDN do pool de front-ends (por exemplo, lyncpool01. contoso. local).

8.  Na página **detalhes da publicação interna** , em **caminho (opcional)**, digite ** / ** como o caminho da pasta a ser publicada e, em seguida, selecione encaminhar **o cabeçalho original do host**.

9.  Na página de **detalhes do nome público** , faça o seguinte:
    
      - Em **aceitar solicitações por**, selecione **este nome de domínio**.
    
      - Em **nome público**, digite **lyncdiscover.** \<sipdomain\> (a URL do serviço de descoberta automática externa). Se você estiver criando uma regra para a URL de serviços Web externos no pool de front-ends, digite o FQDN dos serviços Web externos em seu pool de front-ends (por exemplo, lyncwebextpool01.contoso.com).
    
      - Em **caminho**, digite ** / **.

10. Na página **selecionar ouvinte da Web** , no **ouvinte da Web**, selecione seu ouvinte SSL existente com o certificado público atualizado.

11. Na página **delegação de autenticação** , selecione **sem delegação, mas o cliente pode autenticar diretamente**.

12. Na página **conjunto de usuários** , selecione **todos os usuários**.

13. Na página **concluindo o assistente de nova regra de publicação na Web** , verifique se as configurações da regra de publicação da Web estão corretas e clique em **concluir**.

14. Na lista do Forefront TMG de regras de publicação na Web, clique duas vezes na nova regra que você acabou de adicionar para abrir **as propriedades**.

15. Na guia **para** , faça o seguinte:
    
      - Selecione **encaminhar o cabeçalho original do host em vez do verdadeiro**.
    
      - **As solicitações selecionadas parecem vir do computador com o FOREFRONT TMG**.

16. Na guia **ponte** , configure o seguinte:
    
      - Selecione **servidor Web**.
    
      - Selecione **redirecionar solicitações para porta http**e digite **8080** para o número da porta.
    
      - Selecione **redirecionar solicitações para porta SSL**e digite **4443** para o número da porta.

17. Clique em **OK**.

18. Clique em **aplicar** no painel detalhes para salvar as alterações e atualizar a configuração.

19. Clique em **testar regra** para verificar se a nova regra está configurada corretamente.

</div>

<div>

## <a name="to-modify-an-existing-web-publishing-rule-to-add-the-external-autodiscover-san-and-url"></a>Para modificar uma regra de publicação da Web existente para adicionar a SAN e a URL de descoberta automática externa

1.  Clique em **Iniciar**, aponte para **programas**, aponte para **Microsoft Forefront TMG**e clique em **Gerenciamento do Forefront TMG**.
    
    <div>
    

    > [!IMPORTANT]  
    > Você irá repetir a modificação para cada regra de publicação e ouvinte que você tiver. Geralmente, isso será uma regra e um ouvinte para os pools de front-end e um para os directors opcionais ou os pools de directors, se você os tiver implantado.

    
    </div>

2.  No painel esquerdo, expanda **ServerName**, clique com o botão direito do mouse em **política de firewall**, clique na regra aplicável. Na guia **tarefas** , clique em **Editar regra selecionada**.

3.  Na guia **nome público** , nesta **regra aplica-se a**, selecione **solicitações para os seguintes sites da Web**.

4.  Clique em **Adicionar**, digite o nome do novo site de descoberta automática (por exemplo, "lyncdiscover.contoso.com") e clique em **OK**.

5.  Na guia **ouvinte** , clique em **Selecionar certificado** e atribua o novo certificado às entradas adicionadas de San de descoberta automática. Feche as propriedades do ouvinte e publicação na Web.

6.  Clique em **aplicar** no painel detalhes para salvar as alterações e atualizar a configuração.

7.  Clique em **testar regra** para verificar se a nova regra está configurada corretamente.

</div>

<div>

## <a name="to-create-a-web-publishing-rule-for-port-80"></a>Para criar uma regra de publicação na Web para a porta 80

1.  Clique em **Iniciar**, aponte para **programas**, aponte para **Microsoft Forefront TMG**e clique em **Gerenciamento do Forefront TMG**.

2.  No painel esquerdo, expanda **ServerName**, clique com o botão direito do mouse em **política de firewall**, aponte para **novo**e clique em regra de **publicação de site da Web**.

3.  Na página **Bem-vindo à nova regra de publicação na Web** , digite um nome para exibição para a nova regra de publicação (por exemplo, descoberta automática do LYNC (http)).

4.  Na página **Selecionar ação da regra** , selecione **permitir**.

5.  Na página **tipo de publicação** , selecione **publicar um único site da Web ou um balanceador de carga**.

6.  Na página **segurança de conexão do servidor** , selecione **usar conexões não seguras para se conectar ao servidor Web ou ao farm de servidores publicado**.

7.  Na página **detalhes da publicação interna** , em **nome do site interno**, digite o FQDN de serviços Web internos para o seu pool de front-end (por exemplo, lyncpool01. contoso. local).

8.  Na página **detalhes da publicação interna** , em **caminho (opcional)**, digite ** / ** como o caminho da pasta a ser publicada e, em seguida, selecione encaminhar **o cabeçalho do host original em vez do especificado no campo nome do site interno **.

9.  Na página de **detalhes do nome público** , faça o seguinte:
    
      - Em **aceitar solicitações por**, selecione **este nome de domínio**.
    
      - Em **nome público**, digite **lyncdiscover.** \<sipdomain\> (a URL do serviço de descoberta automática externa).
    
      - Em **caminho**, digite ** / **.

10. Na página **selecionar ouvinte da Web** , no **ouvinte da Web**, selecione um ouvinte da Web ou use o assistente de definição novo ouvinte da Web para criar um novo.

11. Na página **delegação de autenticação** , selecione **sem delegação e o cliente não pode autenticar diretamente**.

12. Na página **conjunto de usuários** , selecione **todos os usuários**.

13. Na página **concluindo o assistente de nova regra de publicação na Web** , verifique se as configurações da regra de publicação da Web estão corretas e clique em **concluir**.

14. Na lista do Forefront TMG de regras de publicação na Web, clique duas vezes na nova regra que você acabou de adicionar para abrir **as propriedades**.

15. Na guia **ponte** , configure o seguinte:
    
      - Selecione **servidor Web**.
    
      - Selecione **redirecionar solicitações para porta http**e digite **8080** para o número da porta.
    
      - Verifique se **a seleção redirecionar solicitações para a porta SSL** não está selecionada.

16. Clique em **OK**.

17. Clique em **aplicar** no painel detalhes para salvar as alterações e atualizar a configuração.

18. Clique em **testar regra** para verificar se a nova regra está configurada corretamente.

19. Verifique se a URL do serviço de descoberta automática externa não está definida em nenhuma outra regra de publicação na Web.

</div>

<div>

## <a name="see-also"></a>Confira também


[Configurando servidores de proxy reverso para o Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

