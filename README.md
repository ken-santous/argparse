# argparse
 
import argparse  
from glob import glob  

def main(file_names):  
    print file_names  

if __name__ == "__main__":  
    parser = argparse.ArgumentParser()  
    parser.add_argument("file_names", nargs='*') 
    #nargs='*' to combine all positional arguments into a single list 

    args = parser.parse_args()  
    file_names = []

    # use glob to find files matching wildcards
    #if a string does not contain a wildcard, glob will return it as is.
    for arg in args.file_names:  
        file_names += glob(arg)
