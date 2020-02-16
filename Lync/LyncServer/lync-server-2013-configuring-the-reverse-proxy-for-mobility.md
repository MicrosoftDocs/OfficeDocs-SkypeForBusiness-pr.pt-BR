---
title: 'Lync Server 2013: Configurando o proxy reverso para mobilidade'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the reverse proxy for mobility
ms:assetid: 3f4a9e33-77e4-4c18-a73f-24d4bec8ea9c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690011(v=OCS.15)
ms:contentKeyID: 48183946
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f37da0858cde92cb28b5f7b67421a49ae77d211
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029984"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-reverse-proxy-for-mobility-in-lync-server-2013"></a>Configurando o proxy reverso para mobilidade no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-03-20_

Se você quiser usar a descoberta automática para clientes do dispositivo móvel, precisará modificar ou criar uma nova regra de publicação na Web para o proxy reverso quer você atualize ou não as listas de nome alternativo de assunto nos certificados de proxy reverso.

Se você decidir usar HTTPS para solicitações iniciais do serviço de descoberta automática do Lync Server 2013 e atualizar as listas de nomes alternativos de entidade nos certificados de proxy reverso, você precisará atribuir o certificado público atualizado ao ouvinte SSL (Secure Sockets Layer) no seu proxy reverso. Para obter detalhes sobre as entradas de nome alternativo de entidade necessárias, consulte [Technical Requirements for Mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md). Em seguida, você precisa modificar o ouvinte existente para serviçso da Web externos ou criar uma nova regra de publicação para o URL do Serviço Descoberta Automática externo. Se você ainda não tiver uma regra de publicação na Web para a URL dos serviços Web externos do Lync Server 2013 para seu pool de front-ends, você também precisará publicar uma regra para isso.

<div>


> [!NOTE]  
> A regra de publicação de proxy reversa e o ouvinte podem fornecer serviços tanto para Web externa quanto para o Serviço de Descoberta Automática, desde que o certificado atribuído ao ouvinte possua o nome de assunto necessário e os nomes alternativos de assunto para ambos. Para obter detalhes sobre a configuração padrão do ouvinte da Web e da regra de publicação, confira <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Configurando servidores de proxy reverso para o Lync Server 2013</A> para obter mais detalhes.



</div>

Se você decidir usar HTTP para solicitações iniciais de Serviço Descoberta Automática para que não precise atualizar nomes alternativos de assunto para o proxy reverso, você precisará criar ou modificar uma regra de publicação na Web para a porta 80.

Os procedimentos nesta seção descrevem como criar ou modificar as regras de publicação na Web no Microsoft Forefront Threat Management Gateway 2010 para descoberta automática.

<div>


> [!NOTE]  
> Esses procedimentos assumem que você possui a Standard Edition do Forefront Threat Management Gateway (TMG) 2010 instalado. Se você estiver utilizando outro proxy reverso, os procedimentos são similares, mas precisarão ser mapeados para a documentação do produto de terceiro.



</div>

<div>

## <a name="to-create-a-web-publishing-rule-for-the-external-autodiscover-url"></a>Para criar uma regra de publicação na Web para a URL externa de Descoberta Automática

1.  Clique em **Iniciar**, aponte para **Programas**, **Microsoft Forefront TMG** e, então, clique em **Forefront TMG Management**.

2.  No painel esquerdo, expanda **Nome do Servidor**, clique com o botão direito do mouse em **Diretiva de Firewall**, aponte para **Novo** e clique em **Regra de Publicação de Site**.

3.  Na página **Bem-vindo à nova regra de publicação na Web**, digite um nome para exibição para a nova regra de publicação (por exemplo, LyncDiscoveryURL).

4.  Na página **Selecionar Ação de Regra**, selecione **Permitir**.

5.  Na página **Tipo de Publicação**, selecione **Publicar um único site da Web ou balanceador de carga**.

6.  Na página **Segurança da Conexão do Servidor**, selecione **Usar SSL para conectar ao servidor Web ou ao farm de servidores publicado**.

7.  Na página **detalhes de publicação interna** , em **nome do site interno**, digite o nome de domínio totalmente qualificado (FQDN) do seu pool de diretor (por exemplo, lyncdir01. contoso. local). Se você estiver criando uma regra para a URL de serviços Web externos no pool de front-ends, digite o endereço VIP do balanceador de carga de hardware (HLB) na frente do pool de front-ends.

8.  Na página **detalhes de publicação interna** , em **caminho (opcional)**, digite ** / ** como o caminho da pasta a ser publicada e, em seguida, selecione **encaminhar o cabeçalho de host original**.

9.  Na página **Detalhes do Nome Público**, faça o seguinte:
    
      - Em **Aceitar Solicitações para**, selecione **Este nome de domínio**.
    
      - Em **nome público**, digite **lyncdiscover.** \<sipdomain\> (a URL externa do serviço de descoberta automática). Se você estiver criando uma regra para a URL de serviços Web externos no pool de front-ends, digite o FQDN dos serviços Web externos em seu pool de front-ends (por exemplo, lyncwebextpool01.contoso.com).
    
      - Em **caminho**, digite ** / **.

10. Na página **Selecionar Ouvinte da Web**, no **Ouvinte da Web**, selecione o Ouvinte SSL existente com o certificado público atualizado.

11. Na página **Delegação de Autenticação**, selecione **Nenhuma delegação, mas o cliente pode autenticar diretamente**.

12. Na página **Conjunto de Usuários**, selecione **Todos os Usuários**.

13. Na página **Concluindo o Assistente de Nova Regra de Publicação de Web**, verifique se as configurações da regra de publicação de Web estão corretas e clique em **Concluir**.

14. Na lista Forefront TMG de regras de publicação, clique duas vezes na nova regra que você acabou de adicionar para abrir **Propriedades**.

15. Na guia **Para**, faça o seguinte:
    
      - Selecione **Encaminhar o cabeçalho de host original em vez do presente**.
    
      - Selecione **As solicitações parecem vir de computador do Forefront TMG**.

16. Na guia **Ponte**, configure o seguinte:
    
      - Selecione **Servidor Web**.
    
      - Selecione **Redirecionar solicitações para a porta HTTP** e digite **8080** como número da porta.
    
      - Selecione   **Redirecionar solicitações para a porta SSL** e digite **4443** para o número da porta.

17. Clique em **OK**.

18. Clique em **Aplicar** no painel de detalhes para salvar as alterações e atualizar a configuração.

19. Clique em **Regra de Teste** para verificar se a nova regra está definida corretamente.

</div>

<div>

## <a name="to-modify-an-existing-web-publishing-rule-to-add-the-external-autodiscover-san-and-url"></a>Para modificar uma regra de publicação Web existente para adicionar o SAN de Descoberta Automática externa e URL

1.  Clique em **Iniciar**, aponte para **Programas**, aponte para **Microsoft Forefront TMG** e clique em **Gerenciamento do Forefront TMG**.
    
    <div>
    

    > [!IMPORTANT]  
    > Você irá repetir a modificação para cada regra de publicação e ouvinte que possuir. Normalmente, será uma regra e um ouvinte para os pools de front-ends e um para os diretores opcionais ou pools de diretores, se você os tiver implantado.

    
    </div>

2.  No painel à esquerda, expanda **ServerName**, clique com o botão direito em **Política de firewall** e clique na regra aplicável. Na aba **Tarefas**, clique na **regra Editar selecionado**.

3.  Na aba **Nome público**, em **Esta regra se aplica a**, selecione **Solicitações para os seguintes sites da Web**.

4.  Clique em **Adicionar**, digite o nome do site de Descoberta Automática novo (por exemplo, “lyncdiscover.contoso.com”) e clique em **OK**.

5.  Na aba **Ouvinte**, clique em **Selecionar certificado** e atribua o novo certificado com as entradas SAN da Descoberta Automática adicionadas. Feche o Ouvinte e as propriedades de Publicação na Web.

6.  Clique em **Aplicar** no painel de detalhes para salvar as alterações e atualizar a configuração.

7.  Clique em **Testar regra** para verificar se a nova regra foi definida corretamente.

</div>

<div>

## <a name="to-create-a-web-publishing-rule-for-port-80"></a>Para criar uma regra de publicação na Web para a porta 80

1.  Clique em **Iniciar**, aponte para **Programas**, **Microsoft Forefront TMG** e, então, clique em **Forefront TMG Management**.

2.  No painel esquerdo, expanda **Nome do Servidor**, clique com o botão direito do mouse em **Diretiva de Firewall**, aponte para **Novo** e clique em **Regra de Publicação de Site**.

3.  Na página **Bem-vindo à nova regra de publicação na Web**, digite um nome para exibição para a nova regra de publicação (por exemplo, Descoberta Automática do Lync (HTTP)).

4.  Na página **Selecionar Ação de Regra**, selecione **Permitir**.

5.  Na página **Tipo de Publicação**, selecione **Publicar um único site ou um balanceador de carga na Web** e clique em Avançar.

6.  Na página **Segurança da Conexão do Servidor**, selecione **Usar conexões não seguras para conectar ao servidor Web ou ao farm de servidores publicado**.

7.  Na página **detalhes de publicação interna** , em **nome do site interno**, digite o endereço VIP do balanceador de carga de hardware (HLB) na frente do pool de front-ends.

8.  Na página **detalhes de publicação interna** , em **caminho (opcional)**, digite ** / ** como o caminho da pasta a ser publicada e, em seguida, selecione **encaminhar o cabeçalho de host original em vez do especificado no campo nome do site interno**.

9.  Na página **Detalhes do Nome Público**, faça o seguinte:
    
      - Em **Aceitar Solicitações para**, selecione **Este nome de domínio**.
    
      - Em **nome público**, digite **lyncdiscover.** \<sipdomain\> (a URL externa do serviço de descoberta automática).
    
      - Em **caminho**, digite ** / **.

10. Em **Selecionar Ouvinte da Web**, em **Ouvinte da Web**, selecione um Ouvinte da Web ou use o Assistente de Nova Definição de Ouvinte da Web para criar um novo.

11. Na página **Delegação de Autenticação**, selecione **Nenhuma delegação, e o cliente não pode autenticar diretamente**.

12. Na página **Conjunto de Usuários**, selecione **Todos os Usuários**.

13. Na página **Concluindo o Assistente de Nova Regra de Publicação de Web**, verifique se as configurações da regra de publicação de Web estão corretas e clique em **Concluir**.

14. Na lista Forefront TMG de regras de publicação, clique duas vezes na nova regra que você acabou de adicionar para abrir **Propriedades**.

15. Na guia **Ponte**, configure o seguinte:
    
      - Selecione **Servidor Web**.
    
      - Selecione   **Redirecionar solicitações para a porta HTTP** e digite **8080** para o número da porta.
    
      - Verifique se **Redirecionar solicitações para a porta SSL** não está selecionada.

16. Clique em **OK**.

17. Clique em **Aplicar** no painel de detalhes para salvar as alterações e atualizar a configuração.

18. Clique em **Regra de Teste** para verificar se a nova regra está definida corretamente.

19. Verifique se a URL do Serviço Descoberta Automática externo não está definida em nenhuma outra regra de publicação na Web.

</div>

<div>

## <a name="see-also"></a>Confira Também


[Configurando servidores de proxy reverso para o Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md)  
[Requisitos técnicos para mobilidade no Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

