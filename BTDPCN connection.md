# connection doc
  https://docs.databricks.com/en/dev-tools/python-sql-connector.html

# demo code
~~~ python
from databricks import sql
import pandas as pd
from rmfs.utils import cfg

conn= sql.connect (server_hostname=cfg.data_server["server_hostname"],
                    http_path=cfg.data_server["http_path"],
                access_token=cfg.data_server["access_token"])


def querybtdpcn():
    sql_test="""select * from riads.v_dim_ri_iscreening_question"""
    df=pd.read_sql(sql_test, conn)
    print (df.head(6))




querybtdpcn()




~~~

