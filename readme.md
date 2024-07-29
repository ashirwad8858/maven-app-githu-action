mvn clean test

open target/site/jacoco/index.html

- name: Build with Maven
      run: mvn clean test

    - name: Generate JaCoCo report
      run: mvn jacoco:report

    - name: Upload JaCoCo report
      uses: actions/upload-artifact@v2
      with:
        name: jacoco-report
        path: target/site/jacoco

  - name: Generate JaCoCo report
      run: mvn jacoco:report

    - name: Upload coverage to Codecov
      uses: codecov/codecov-action@v2
      with:
        token: ${{ secrets.CODECOV_TOKEN }}
        files: target/site/jacoco/jacoco.xml
        fail_ci_if_error: true
        verbose: true


////////////////////////////////////////
      mvn clean test jacoco:report
sudo apt install xdg-utils

xdg-open target/site/jacoco/index.html

- name: Build with Maven
      run: mvn clean test

    - name: Generate JaCoCo report
      run: mvn jacoco:report

    - name: Upload JaCoCo report
      uses: actions/upload-artifact@v2
      with:
        name: jacoco-report
        path: target/site/jacoco
