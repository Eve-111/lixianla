# lixianla
lixianla.com auto sign task


# �Զ�������

�Ƽ��������ƺ�����

# Github Action
��clone����Ŀ������push��private��Ŀ������й¶���ݣ������ͷ��������fork��������Ӧ���ݡ�


ʹ��Github Action�Զ�������Ҳ�����[�����ӳ�](https://zhuanlan.zhihu.com/p/379365305)

���ݲ��ԣ�Github Acion�����������л������������Ҫ����30s���ң��������0��׼ʱ�򿨵����������ȿ����ƺ�������·�ɲ���

��Acion�н���Ϊmain����ִ��30s�����ӳ٣�����crontab��ǰΪÿ��23:59���У�ע��ʱ�����⣬����ʱ���Github��ʹ��ʱ����8��Сʱ���������Ͽ��Խ�������⣬δ�����ԣ����������顣

# workflows
```yaml
name: auto_task

on:
  schedule:
    - cron: "0 16 * * *"

  workflow_dispatch:

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - uses: actions/checkout@v2
      - name: Set up Python 3.9
        uses: actions/setup-python@v2
        with:
                python-version: 3.9
                
                
      - name: Install dependencies
        run: |
              python -m pip install --upgrade pip
              pip install requests
              pip install ddddocr
              pip install bs4
      
      - name: Sign Task
        run: |
              python main.py
```

# ע������
����[���ɿ��ܵ�����](https://work.weixin.qq.com/nl/act/p/32d807ad4c554975)����ҵ΢�����ͷ�ʽ���ã��л�Ϊ���������ˡ�������Ҫ�����в鿴commits

������Ӧ����2022��6��20��֮ǰ����������ӵ��һ���̶��Ĺ����Ƿ�����IP������ʹ����ҵ΢�Ž��У��������۵ģ�ͼ�����͡�
